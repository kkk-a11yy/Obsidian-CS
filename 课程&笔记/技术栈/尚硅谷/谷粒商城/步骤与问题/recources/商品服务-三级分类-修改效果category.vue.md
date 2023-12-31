```java
<!--  -->
<template>
    <div>
        <el-tree :data="menus" :props="defaultProps" :expand-on-click-node="false" show-checkbox node-key="catId"
            :default-expanded-keys="expendedkey">

            <span class="custom-tree-node" slot-scope="{ node, data }">
                <span>{{ node.label }}</span>
                <span>
                    <el-button v-if="node.level <= 2" type="text" size="mini" @click="() => append(data)">
                        Append
                    </el-button>
                    <el-button type="text" size="mini" @click="edit(data)">
                        Edit
                    </el-button>
                    <el-button v-if="node.childNodes.length == 0" type="text" size="mini" @click="() => remove(node, data)">
                        Delete
                    </el-button>
                </span>
            </span>
        </el-tree>
        <el-dialog :title="title" :visible.sync="dialogVisible" width="30%" :close-on-click-modal="false">
            <el-form :model="category">
                <el-form-item label="分类名称">
                    <el-input v-model="category.name" autocomplete="off"></el-input>
                </el-form-item>
                <el-form-item label="图标">
                    <el-input v-model="category.icon" autocomplete="off"></el-input>
                </el-form-item>
                <el-form-item label="计量单位">
                    <el-input v-model="category.productUnit" autocomplete="off"></el-input>
                </el-form-item>
            </el-form>
            <span slot="footer" class="dialog-footer">
                <el-button @click="dialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="SubmitData">确 定</el-button>
            </span>
        </el-dialog>
    </div>
</template>

<script>
//这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
//例如：import 《组件名称》 from '《组件路径》';

export default {
    //import引入的组件需要注入到对象中才能使用
    components: {},
    data() {
        return {
            title: "",
            dialogType: "",//append,edit
            category: {
                name: "",
                parentCid: 0,
                catLevel: 0,
                showStatus: 1,
                sort: 0,
                icon: "",
                productUnit: "",
                catId: null
            },
            menus: [],
            dialogVisible: false,
            expendedkey: [],
            defaultProps: {
                children: 'children',
                label: 'name'
            }
        };
    },
    methods: {

        getMenus() {
            this.$http({
                url: this.$http.adornUrl('/product/category/list/tree'),
                method: 'get',

            }).then(({ data }) => {
                console.log("成功获取到菜单数据。。。", data.data)
                this.menus = data.data;
            });
        },
        edit(data) {
            console.log("要修改的数据", data);
            this.title = "修改分类";
            this.dialogVisible = true;
            this.dialogType = "edit";
            //发送请求获得最新数据
            this.$http({
                url: this.$http.adornUrl(`/product/category/info/${data.catId}`),
                method: 'get',
            }).then(({ data }) => {
                //请求成功
                //TODO:这里的data.name;
                console.log("要回显的数据", data)
                this.category.name = data.category.name;
                this.category.catId = data.category.catId;
                this.category.icon = data.category.icon;
                this.category.productUnit = data.category.productUnit;
                this.category.parentCid = data.category.parentCid;
                this.category.catLevel = data.category.catLevel;
                this.category.sort = data.category.sort;
                this.category.showStatus = data.category.showStatus;
            })

        },

        append(data) {
            console.log("append", data);
            this.title = "添加分类";
            this.dialogType = "add";
            this.dialogVisible = true;
            this.category.parentCid = data.catId;
            this.category.catLevel = data.catLevel * 1 + 1;
            this.category.catId = null;
            this.category.name = "";
            this.category.icon = "";
            this.category.productUnit = "";
            this.category.sort = 0;
            this.category.showStatus = 1;
        },
        SubmitData() {
            if (this.dialogType == "add") {
                this.addCategory();
            }
            if (this.dialogType == "edit") {
                this.editCategory();
            }
        },
        //修改三级分类数据
        editCategory() {
            var { catId, name, icon, productUnit } = this.category;
            this.$http({
                url: this.$http.adornUrl('/product/category/update'),
                method: 'post',
                data: this.$http.adornData({ catId, name, icon, productUnit }, false)
            }).then(({ data }) => {
                this.$notify({
                    title: '成功',
                    message: '菜单修改成功',
                    type: 'success'
                });
                //关闭对话框
                this.dialogVisible = false;
                //刷新出新的菜单
                this.getMenus();
                //设置需要默认展开的菜单
                this.expendedkey = [this.category.parentCid];
            });
        },
        //添加三级分类  
        addCategory() {
            console.log("提交的三级分类数据", this.category);
            this.$http({
                url: this.$http.adornUrl('/product/category/save'),
                method: 'post',
                data: this.$http.adornData(this.category, false)
            }).then(({ data }) => {
                this.$notify({
                    title: '成功',
                    message: '菜单保存成功',
                    type: 'success'
                });
                //关闭对话框
                this.dialogVisible = false;
                //刷新出新的菜单
                this.getMenus();
                //设置需要默认展开的菜单
                this.expendedkey = [this.category.parentCid];
            });

        },


        remove(node, data) {
            var ids = [data.catId]
            this.$confirm(`是否删除【${data.name}】菜单？`, '提示', {
                confirmButtonText: '确定',
                cancelButtonText: '取消',
                type: 'warning'
            }).then(() => {
                this.$http({
                    url: this.$http.adornUrl('/product/category/delete'),
                    method: 'post',
                    data: this.$http.adornData(ids, false)
                }).then(({ data }) => {
                    this.$notify({
                        title: '成功',
                        message: '菜单删除成功',
                        type: 'success'
                    });
                    //刷新出新的菜单
                    this.getMenus();
                    //设置需要默认展开的菜单
                    this.expendedkey = [node.parent.data.catId]
                });
            }).catch(() => {

            })
            console.log("remove", node, data);
        },

    },


    //监听属性 类似于data概念
    computed: {},
    //监控data中的数据变化
    watch: {},
    //方法集合

    //生命周期 - 创建完成（可以访问当前this实例）
    created() {
        this.getMenus();

    },
    //生命周期 - 挂载完成（可以访问DOM元素）
    mounted() {

    },
    beforeCreate() { }, //生命周期 - 创建之前
    beforeMount() { }, //生命周期 - 挂载之前
    beforeUpdate() { }, //生命周期 - 更新之前
    updated() { }, //生命周期 - 更新之后
    beforeDestroy() { }, //生命周期 - 销毁之前
    destroyed() { }, //生命周期 - 销毁完成
    activated() { }, //如果页面有keep-alive缓存功能，这个函数会触发
}
</script>

<style scoped></style>



```