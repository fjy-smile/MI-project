<template>
		<div class="home-brick-box">
  			<div class="box-hd">
  				<h2>手机</h2>
  				<div class="more"><a href="#">查看全部<div class="iconf">&gt</div></a></div>
  			</div>
  			<div class="box-bd clearfix">
  				<div class="span4"><a href="#"></a></div>
  				<div class="span16">
  					<ul>
 						<li v-for="(site,index) in hBB1" :key="index">
  							<a href="#">
  								<div class="figure"><img :src="site.url"></div>
  								<h4 class="title">{{site.title}}</h4>
  								<p class="desc">{{site.desc}}</p>
  								<p class="price">{{site.price}}</p>
  							</a>
  						</li>
  					</ul>
  				</div>
  			</div>
  		</div>
</template>
<script type="text/javascript">
	export default{
		name:'homeBrickBox',
		props:["hBB1","hBB2"],
		data(){
			return{
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
          width:90px;
          top:0;
          right: 10px;
          a{
            text-decoration: none;
            color:#000;
            .iconf{
              float: right;
              font-size: 20px;
            }
          }
          a:hover{
            color: #ff6700;
          }
        }
      }
      .box-bd{
        height: 648px;
        width: 1226px;
        .span4{
          height: 614px;
          width: 234px;
          background: url(../assets/home-brick-box1/brick-item.jpg);
          float: left;
          a{
            display: block;
            height: 614px;
            width: 100%;
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
          }
        }
      }
    }
</style>