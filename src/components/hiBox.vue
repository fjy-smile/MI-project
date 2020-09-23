<template>
	<div class="hiBox" ref="hiBox" @mouseleave="moveOutMethods">
		<ul>
			<li ref="Bindex" v-for="(site,index) in Box.slice(0,5)" :key="index">
  				<a href="#">
  				    <div class="figure"><img class="img":src="site.url"></div>
  					<h4 class="title">{{site.title}}</h4>
  					<p class="price">{{site.price}}</p>
  				</a>
  			</li>
		</ul>
	</div>


</template>
<script type="text/javascript">
	export default{
		name:'hiBox',
		data(){
			return{
				 Box:[],
			}
		},
		props:['dataFromFather','Box'],
		methods:{
			bortherMethods(){
				this.$refs.hiBox.style.display="block"
			},
			moveOutMethods(){
				this.$refs.hiBox.style.display="none"
			}

		},
		computed:{
			
		}
	}
</script>
<style lang="less" scoped>
	.hiBox{
		height: 230px;
		width:100%;
		background: #fff;
		display: none;
	    ul{
		    height: 230px;
		    width: 100%;
		    li{
		        list-style: none;
		        float: left;
		        height: 200px;
		        width: 200px;
		        background: #fff;
		        margin-bottom: 14px;
		        margin-left: 14px;
		        a{
			        height: 200px;
			        width: 200px;
			        display: block;
			        text-decoration: none;
			        .figure{
			            height: 120px;
			            width: 160px;
			            margin:auto;
			            img{
			            	display: block;
			            	height: 120px;
			            	width: 120px;
			            	margin:auto;
			            }
			        }
			        .title{
			        font-weight: normal;
			        text-align: center;
			        color: #000;
			        margin-bottom: 0px;
			        }
			        .desc{
			            color:#b0b0b0;
			            font-size: 12px;
			            text-align: center;
			        }
			        .price{
			            color: #ff6700;
			            text-align: center;
			            font-size: 14px;
			        }
			    }
		    }
		          
	    }
	}
</style>