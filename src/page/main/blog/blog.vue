<template>
	<div class="blog-content">
		<h2 class="blog-topic" @click="click">贫穷，也会限制我们的格局和眼界</h2>
		<div class="blog-tagTime">
			<span class="blog-tag fa fa-remove"></span>
			<span class="blog-time" @click="clic1">2013.01.02</span>
		</div>
		<p class="blog-content-article"></p>
	</div>
</template>
<script>
//import message from '@/common/plugins/message'
	export default{
		created(){
			var params = new URLSearchParams();
			let me=this;
			params.append('UserId', '521dd');
			this.$ajax({
				method:'post',
				url:'/getuser',
				data:{
					UserId:'521dd',
					UserName:'sss',
					age:17
				}
			}).then(function(res){
					console.log(res)
			})
			.catch(function(e){
				
			})
		},
		methods:{
			click(){
				// this.$notifi({
				// 		type:'war'
				// });
				this.$message({
					type:'confirm',
					message:' 你怎么可以这样',
					okFun:function(a){
						console.log(a);
					}
				})
			},
			clic1(){
				// this.$notifi({
				// 		type:'success'
				// });
			}
		},
		// components:{
		// 	message
		// },
	}
</script>
<style>
.blog-content{
	width:800px;
	margin:20px auto;
	height: 4000px;
}
.blog-topic{
	width:100%;
	text-align: center;
	line-height: 30px;
}
.blog-tagTime{
	width:150px;
	height:40px;
	margin:0 auto;
	line-height: 40px;
}
.blog-tag{

}
.blog-time{
	display: inline-block;
    padding-left: 3px;
    color: #969696;
    vertical-align: middle;
}
</style>