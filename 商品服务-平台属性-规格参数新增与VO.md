# 模糊查询

![](BEFORE/附件/Pasted%20image%2020231126195358.png)[](BEFORE/附件/Pasted%20image%2020231126195325.png)
- `AttrGroupServiceImpl: public PageUtils queryPage()` 进行模糊查询

# 规格参数-新增

![](BEFORE/附件/Pasted%20image%2020231126201314.png)

- 提交后：`http://localhost:88/api/product/attr/save`
- 数据库：`pms_attr` 的 `attr_id` 没有，`pms_attr_attrgroup_relation` 也没有数据
- ![](BEFORE/附件/Pasted%20image%2020231126201918.png)
- `AttrEntity: @JsonInclude(JsonInclude.Include.NON_EMPTY) @TableField(exist = false) private Long attrGroupId`