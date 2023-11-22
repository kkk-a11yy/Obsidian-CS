- 老师的 `upload`文件夹复制到 `renren-fast-vue/../src/components/` 文件夹下
- 复制 Bucket 域名：`andymall.oss-cn-shanghai.aliyuncs.com`
	- 替换：multiUpload.vue. ; singleUpload.vue
		- `<el-upload action=`
	- `view/s/modules/product/brand-add-or-upload`
		- `<script> import singleUpload from '@/components/upload/singleUpload';`
		- `export default {components:{singleUpload},`
		- `<single-upload v-model="dataForm.logo"></single-upload>`
- `OssController`
	- `R polic(){}`
- 阿里云 bucket 配置允许跨域访问
- ![](BEFORE/附件/Pasted%20image%2020231121155406.png)

- 到现在，文件上传就不用经过自己的服务器了

下一个：[商品服务-品牌管理-品牌新增与修改](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/商品服务-品牌管理-品牌新增与修改.md)
