- element:  scoped slot
	- `:expand-on-click-node="false" show-checkbox node-key="catId"`
	- 复制 `<span>` 标签的内容，放到 category.vue 的 `<el-tree>` 当中
	- 复制 `append` 、`remove` 方法到 `methods`
	- 只有一级二级菜单显示`append` ,三级分类显示 `delete`
		- `v-if="node.level <=2"`
		- `v-if="node.childNodes.length==0"`

下一个：[商品服务-三级分类-tree删除--逻辑](商品服务-三级分类-tree删除--逻辑.md)