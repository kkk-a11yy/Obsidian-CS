# 模糊查询

![](BEFORE/附件/Pasted%20image%2020231126195358.png)[](BEFORE/附件/Pasted%20image%2020231126195325.png)
- `AttrGroupServiceImpl: public PageUtils queryPage()` 进行模糊查询

# 规格参数-新增

![](BEFORE/附件/Pasted%20image%2020231126201314.png)

- 提交后：`http://localhost:88/api/product/attr/save`
- 数据库：`pms_attr` 的 `attr_id` 没有，`pms_attr_attrgroup_relation` 也没有数据
- ![](BEFORE/附件/Pasted%20image%2020231126201918.png)
- 不推荐这个： 
	- `AttrEntity: @JsonInclude(JsonInclude.Include.NON_EMPTY) @TableField(exist = false) private Long attrGroupId`
- 引入VO
	- `AttrServiceImpl: public void saveAttr(){}`
- 测试： 新增规格参数：` http://localhost:88/api/product/attr/save`
- 数据库：`pms_attr_attrgroup_relation` 数据改变
	- ![](BEFORE/附件/Pasted%20image%2020231126220212.png)

下一个：[商品服务-平台属性-规格参数列表](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/商品服务-平台属性-规格参数列表.md)