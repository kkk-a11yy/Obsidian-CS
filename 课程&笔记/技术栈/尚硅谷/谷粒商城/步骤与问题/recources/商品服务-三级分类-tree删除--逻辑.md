http://localhost:88/api/product/category/delete
- CategoryController
	- `categoryService.removeMenuByIds(Arrays.asList(catIds));`
- CategoryServiceImpl
	- `baseMapper.deleteBatchIds(asList);`
- 使用 mybatis-plus (3.2.0)
	- [逻辑删除 | MyBatis-Plus](https://baomidou.com/pages/6b03c5/#%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95)
	- `product` : applucation.yml
		- `logic-delete-value: 1`
		- `logic-not-delete-value: 0`
		- 调整日志级别：`logging: level:  com.andymall: debug`
	- `product` - `CategoryEntity`
		- showStatus:  `@TableLogic(value = "1",delval = "0")`
- ApiPost7 发送post 请求给 `http://localhost:88/api/product/category/delete`  [1431]
- #vue-httpget-httppost-templete(写vue模版)
- element-删除提示框-确认消息
	- 复制 `open(){}` 里面的内容
- element-删除成功-成功提示
- element-tree-`default-expanded-keys` 删除哪一个就默认展开哪一个
- 还原数据库
	- `UPDATE `pms_category` SET show_status=1`

下一个：[商品服务-三级分类-新增效果](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/商品服务-三级分类-新增效果.md)

