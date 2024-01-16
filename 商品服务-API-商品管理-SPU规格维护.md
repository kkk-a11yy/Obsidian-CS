- `/product/attr/base/listforspu/{spuId}`

#P100点击规格找不到页面
	解决：在数据库gulimall_admin执行以下sql再刷新页面即可：【INSERT INTO sys_menu (menu_id, parent_id, name, url, perms, type, icon, order_num) VALUES (76, 37, '规格维护', 'product/attrupdate', '', 2, 'log', 0);】