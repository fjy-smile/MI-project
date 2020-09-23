<template>
		<div class="home-brick-box">
  			<div class="box-hd">
  				<h2>{{kinds}}</h2>
  				<div class="more">
  					<a href="#">热门</a>&nbsp&nbsp&nbsp<a href="#">{{other_type}}</a></div>
  			</div>
  			<div class="box-bd clearfix">
  				<div class="span4">
  					<a href="#"><div class="left-top"></div></a>
  					<a href="#"><div class="left-bottom"></div></a>
  				</div>
  				<div class="span16">
  					<ul>
 						<li v-for="(site,index) in Box" :key="index">
  							<a href="#">
  								<div class="figure"><img :src="site.url"></div>
  								<h4 class="title">{{site.title}}</h4>
  								<p class="desc">{{site.desc}}</p>
  								<p class="price">{{site.price}}</p>
  							</a>
  						</li>
  						<div class="brick-item">
  							<a href="#">
			  					<div class="brick-item-s brick-item-t">
			  						<div class ="figure" href="#">
			  							<img src="../assets/home-brick-box2/r8.jpg"/></div>
			  						<h4 class="title">Air 13.3"2019<br>款</h4>
			  						<p class="price">5699元起</p>
			  					</div>
		  					</a>
		  					<a href="#">
			  					<div class="brick-item-s brick-item-b">
			  						<div class="more">浏览更多<br><small>热门</small></div>
			  						<div class="iconf"></div>
			  					</div>
		  					</a>
  						</div>
  					</ul>

  				</div>
  			</div>
  		</div>
</template>
<script type="text/javascript">
	export default{
		name:'homeBrickBox2',
		props:["Box","kinds","other_type"],
		data(){
			return{
				Box:[],
			}
		},
		methods:{

		},
		computed:{
			
		}
	}
</script>
<style lang="less" scoped>
	.home-brick-box{
      width: 1226px;
      height: 686px;
      margin-top: 22px;
      	.box-hd{
	        height: 58px;
	        width: 100%;
	        position: relative;
	        line-height: 58px;
	        h2{
	          color:#000;
	          font-weight: normal;
	        }
	        .more{
	          position: absolute;
	          font-size: 16px;
	          width:120px;
	          top:0;
	          right: 10px;
	          a{
	            text-decoration: none;
	            color:#000;
	          }
	          a:hover{
	            color: #ff6700;
	            text-decoration: underline;
	          }
	        }
      	}
      	.box-bd{
	        height: 648px;
	        width: 1226px;
	        .span4{
	          height: 614px;
	          width: 234px;
	          float: left;
	          	.left-top{
	          		height: 300px;
	          		width:100%;
	          		background: url(../assets/home-brick-box2/lt.jpg)no-repeat;
	          	}
	          	.left-bottom{
		          	margin-top: 10px;
		          	height: 300px;
		          	width:100%;
		          	background: url(../assets/home-brick-box2/lb.jpg)no-repeat;
	          	}
	          	a{
		            display: block;
		            height: 300px;
		            width: 100%;
		            transition:all 0.1s linear 0s;
	         	}
	         	a:hover{
	                box-shadow:0 10px 10px #f0f0f0;
	                transform: translate(0,-5px);
	            }	            
        	}
	        .span16{
	          height: 614px;
	          width:  992px;
	          float: left;
	         	ul{
		            height: 614px;
		            width: 992px;
		            padding-left: 0px;
		            margin-top:0px;
		            li{
		              list-style: none;
		              float: left;
		              height: 280px;
		              width: 234px;
		              background: #fff;
		              margin-bottom: 14px;
		              margin-left: 14px;
		              padding-top: 20px;
		              	a{
			                height: 280px;
			                width: 234px;
			                display: block;
			                text-decoration: none;
			                transition:all 0.1s linear 0s;
			                .figure{
			                  height: 160px;
			                  width: 160px;
			                  margin:auto;
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
			            a:hover{
			             	box-shadow:0 10px 10px #f0f0f0;
			               	transform: translate(0,-5px);
			            }
		            }
		            .brick-item{
		          		height: 300px;
		          		width: 234px;
		          		float: left; 
		          		margin-left: 14px;
		          		.brick-item-s,a{
		          			height: 143px;
		          			width: 234px;
		          			background: #fff;
		          			margin-bottom:15px;
		          			float: left;
		          		}
		          		.brick-item-t{
		          			.figure{
		          				height: 80px;
		          				width: 80px;
		          				float: right;
		          				margin-right: 15px;
		          				margin-top: 30px;
		          			}
		          			.title{
		          				margin:35px auto 0px 15px;
		          				color: #000;
		          				font-weight: normal;

		          			}
			                .price{
			                  color: #ff6700;
			                  text-align: center;
			                  font-size: 14px;
			                  width: 70px;
			                  margin: 10px 12px;
			                }
		          		}
		          		.brick-item-b{
		          			position: relative;
		          			.more{
		          				margin:45px 1px 0px 15px;
		          				width: 100px;

		          				small{
		          					color: #b0b0b0;
		          				}
		          			}
		          			.iconf{
		          				position: absolute;
		          				top:45px;
		          				right: 25px;
		          				height: 48px;
		          				width: 48px;
		          				background: url(../assets/home-brick-box2/r8-logo.jpg)no-repeat;
		          			}
		          		}
		          		a{
		          			transition:all 0.1s linear 0s;
		          		}
		          		a:hover{
							box-shadow:0 10px 10px #f0f0f0;
			               	transform: translate(0,-5px);		          			
		          		}
	          		}
	          	}

	        }
      }
    }
</style>