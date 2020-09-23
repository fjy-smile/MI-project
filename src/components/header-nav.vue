<template>
	<div class="header-nav">
  		<ul>
  			<li v-for="(item,index) in Nav" :key="item.id"
  				@mouseover="triggerBrotherMethods">
  				<p>{{item.name}}</p>
  			</li>
  		</ul>
  	</div>
</template>
<script type="text/javascript">

	export default{
		name:'headernav',
		data(){
			return{
	     Nav:[
	      	{id:1,name:'小米手机'},
	      	{id:2,name:'Redmi红米'},
	      	{id:3,name:'电视'},
	      	{id:4,name:'笔记本'},
	      	{id:5,name:'家电'},
	      	{id:6,name:'路由器'},
	      	{id:7,name:'智能硬件'},
	      	{id:8,name:'服务'},
	      	{id:9,name:'社区'}],
	      }
		},
		props:['dataFromFather'],
		methods:{
			triggerBrotherMethods(){
				this.$emit('clickBrotherBtn',true)
			},
		},
		computed:{
			
		}
	}
</script>
<style lang="less" scoped>
.header-nav{
	display: table-cell;
	width:65%;
	padding-top: 0px;
	height: 70px;
	ul{
		float: right;
		padding-right: 10px;
		li{
			list-style: none;
			float:left;
			margin-right: 10px;
			font-size:16px;
			p{
				color: #000;
				cursor: pointer;
			}
			p:hover{
				color: #fc5038;
			}
		}
	}
	.hidden_nav{
		width:600px;
		height: 300px;
		background: #678;
	}				
}
</style>