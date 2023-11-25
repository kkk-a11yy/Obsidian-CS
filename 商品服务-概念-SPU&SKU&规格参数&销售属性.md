- 导入 `sql/sys_menus.sql` 到数据库
- 复制文件夹到 `src/views/modules/common`; `src/views/modules/product`
- [01、获取所有分类及子分类 - 谷粒商城 - 易文档](https://easydoc.net/s/78237135/ZUqEdvA4/HqQGp9TI)
- 父子组件：
	- `<category.vue: `
		- `<el-tree...@node-click="nodeclick"`
		- `method: nodeclick(data, node, component) {} ; treenodeclick(){} ; getDataList() {}`
	- `import Category from "../common/category";`
- 后端 Attrgroup: 三级分类查询id
	- `AttrGroupController: R list`
	- `AttrGroupServiceImpl: queryPage(){}`
- 数据库 `pms_attr_group`添加两条 catId为225 的信息，前端对应 `手机`
- 测试get请求
	- `http://localhost:88/api/product/attrgroup/list/1?page=1&key=aaa`
- 导入问题：
	- 右边一直转圈是因为走这个接口的时候后面带了一个catid，去了就行了
	- 转圈的原因是，查询列表的那个接口，如果你是直接使用现成的前端代码，他传了一些参数，你暂时把那些参数给注释掉

![](BEFORE/附件/Pasted%20image%2020231125145601.png)