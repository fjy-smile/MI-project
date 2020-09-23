<template>
  <div>
  	<div id="header">
  		<div class="_topbarBannerWrapper" onclick="alert('你好！')" style='cursor: pointer'>
  		</div>
  		<div class="site-topbar">
  			<div class="ccontainer">
	  			<div class="container">
	  				<div class="box" v-for="site in sites">
	  					<a href="#">{{site.name}}</a></div>
	  			</div>
	  			<div class="_siteUserInfo">
	  				<div class="box" v-for="site in UserInfo">
	  				<a href="#">{{site.name}}&nbsp</a></div>
	  			</div>
	  			<div class="_miniCartTrigger">
	  				<div class="_content" @mouseover="showhidediv"   @mouseout="removeActive"
	  						ref="content"	style='cursor: pointer'>
	  					<a href="#">购物车(0)</a></div>
	  				<div class="_miniCartMenu" ref="menu">购物车中还没有商品，赶紧选购吧！</div>
	  	  		</div>
  	  		</div>
  		</div>
  		<div class="site-header">
  			<div class="container">
  				<div class="header-logo"><a href=" " class="logo"></a></div>
  				<headernav 	@clickBrotherBtn="triggerBrotherMethods" 
  							@clickBrotherBtn2="triggerBrotherMethods2"></headernav>
  				<div class="header-search">
  					<form> 
  						<input class="inbox" type="text"/><input class="insub" type="submit" value=" "/>
  					</form>
  				</div>
  			</div>
  		</div> 
  		<hiBox ref="brother"  :Box="hBB1"></hiBox> 		
  	</div>
  	<div class="home-hero-container">
  		<div class="home-hero">
  			<div class="J_homeSwiper">  
  				<ul class="site-category-list">
  					<a href="#"  v-for="(site,index) in site_category_list" :key="site.id">
  					<li>{{site.name}}<span>&gt</span></li></a>
  				</ul>
  				<div class="swiper-wrapper"><a href="#"><img :src="dataList[currentIndex]"></a></div>
  				<div class="swiper-pagination">
  					<li class="radius" v-for="(item,index) in dataList"
  					@mouseover="gotoPage(index)"
  					:class="{'current':currentIndex == index}"></li></div>
  					<!-- 图片和圆点相同 -->
  				<div class="swiper-button-prev" @click="gotoPage(prevIndex)">&lt</div>
  				<div class="swiper-button-next" @click="gotoPage(nextIndex)">&gt</div>
  			</div>
  			<div class="home-hero-sub">
  				<div class="span4">
  					<div class="sspan" v-for="site in sspan4"><a href="#"><img :src="site.url"/></a></div>
  				</div>
  				<div class="span16">
  					<ul>
  						<li v-for="site in sspan16"><a href="#"><img :src="site.url"></a></li>
  					</ul>
  				</div>
  			</div>
  		</div>
  	</div>
  	<div class="page-main">
  		<div class="container">
  			<div class="home-banner-box home-banner-box1"><a href="#"></a></div>
  			<homeBrickBox :hBB1="hBB1"></homeBrickBox>
  			<div class="home-banner-box home-banner-box2"><a href="#"></a></div>
  			<homeBrickBox2 :Box="hBB2" kinds="家电" other_type="电视影音"></homeBrickBox2>
  			<div class="home-banner-box home-banner-box3"><a href="#"></a></div>
  			<homeBrickBox2 :Box="hBB3" kinds="智能" other_type="安防"></homeBrickBox2>
  		</div>
  	</div>
  	<div class="fixed-box">
  		<dl>
  			<dd>
  				<span class="pict1 box-s"></span></dd>
  			<dd>
  				<span class="pict2 box-s"></span></dd>
  			<dd>
  				<span class="pict3 box-s"></span></dd>
  			<dd>
  				<span class="pict4 box-s"></span></dd>
  			<dd>
  				<span class="pict5 box-s"></span></dd>
  			<dd>
  				<a href="javascript:scroll(0,0)"><span class="pict6 box-s"></span></a></dd>
  		</dl>
  	</div>
  </div>
</template>
<style lang="less" scoped>
#header{
	width:100%;
	position: relative;
	._topbarBannerWrapper{
		height: 120px;
		width:1337px;
		background: url(../assets/pictures/topbarBannerWrapper.jpg)no-repeat;
		margin:0 auto;
	}	
	.site-topbar{
		height: 40px;
		width: 100%;
		background: #333;
		.ccontainer{
			width:1226px;
			height: 40px;
			margin:0 auto;
			.container{
				width:770px;
				display: table;
				float: left;
				font-size:12px;
			}
			._siteUserInfo{
				width:200px;
				display: table;
				float: left;
				margin-left: 130px;
				font-size:12px;
			}
			.box{
				display: table-cell;
				height: 40px;		
				padding:12px 5px 0px 5px;
				a{
					color: #b0b0b0;
					text-decoration: none;
				}
				a:hover{
					color:#fff;
				}
				a:after{
					content:"|";
					padding-left:6px;
					color: #393f3f;
				}
			}
			._miniCartTrigger{
				display: inline-block;
				white-space: nowrap;
				width:120px;
				float: left;
				background: #424242;
				height: 40px;
				text-align: center;
				._content{
					height: 40px;
					line-height: 36px;
					a{
						color: #b0b0b0;
						height: 40px;
						font-size:13px;
						text-decoration: none;
					}
				}
				._miniCartMenu{
					font-size:10px;
					line-height: 70px;
					display:none;
					float: right;
					width:260%;
					height: 78px;
					box-shadow: -1px 1px 1px 1px #ddd;
					background: #fff;
					position: relative;
					z-index: 999;
				}
			}
		}		
	}
	.site-header{
		height: 80px;
		width: 100%;
		margin-top: 0px;
		.container{
			width:1226px;
			margin-left: 4%;
			display: table;			
				margin:auto;
			.header-logo{
				height: 55px;
				width:54px;	
				display: table-cell;
				.logo{
					position: relative;
					display: block;
					overflow: hidden;
					background: #ff6700;
					height: 54px;
					width:55px;
				}
				.logo::before,.logo::after{
					position: absolute;
					left:0;
					top:0;
					height: 55px;
					width:54px;
					content:'';
					transition: transform .4s;
				}
				.logo::before{
					background: url(../assets/pictures/blogo.jpg)no-repeat 50% 50%;
				}
				.logo::after{
					background: url(../assets/pictures/alogo.jpg)no-repeat 50% 50%;
					margin-left: -55px;
				}
				.logo:hover::before,.logo:hover::after{
   					transform: translate(55px);
				}
			}
			.header-search{
				width: 84%;
				height: 48px;
				margin-left: 55px;
				font-size: 0px;
				input{
					outline:none;
					float:left;
				}
				.inbox{
					width: 80%;
					height:43px;
					border:1px solid #ddd;
				}
				.insub{
					width:17%;
					height: 48px;
					background-color:#fff;
					border:1px solid #ddd;
					background: url(../assets/pictures/wsearch.png)no-repeat;
				}
				.insub:hover{
					transition:.3s;
					background: url(../assets/pictures/osearch.png)no-repeat;
				}
				input:hover{
					border:1px solid #aaa;
				}
			}
		}
	}	
	.hiBox{
		position: absolute;
		top:270px;
		z-index: 30;
	}
}
.home-hero-container{
	height: 670px;
	width: 100%;
	margin-top: 30px;
	.home-hero{
		background: #123;
		height: 460px;
		width: 1230px;
		margin:auto;
		.J_homeSwiper{
			height: 460px;
			width:1230px;
			position: relative;
			.site-category-list{
				position:absolute;
				height: 420px;
				width:235px;
				background: #aaa;
				margin-top:0;
				padding-left:0;
				background:rgba(170,170,170,0.5);
				padding-top:40px;
				z-index: 20;
				a{
					font-size: 15px;
					text-decoration: none;
					height: 40px;
					width: 100%;
					display: block;
					line-height: 40px;
					li{
						display: block;
						color: #fff;
						list-style: none;
						margin-left: 25px;
					}
					span{
						margin-right: 40px;
						float:right;
					}
				}
				a:hover{
					background: #ff6700;
				}
				
			}
			.swiper-wrapper{
				height: 460px;
				width:1230px;
				position: absolute;
				background: #aaa;	
				img{
					display: block;
					width: 100%;
				}
			}
			.swiper-pagination{
				position: absolute;
				height: 20px;
				width: 150px;
				right: 10px;
				top:415px;
				right:30px;
				.radius{
					list-style: none;
					float: left;
					margin-right:10px;
					height: 10px;
					width:10px;
					background: #ddd;
					border-radius: 50%;
					box-shadow: 1px 1px 1px 1px #333;
				}
				.current{
					background: #fff;
				}
			}
			.swiper-button-prev,
			.swiper-button-next{
				position: absolute;
				height: 70px;
				width: 40px;
				top:50%;
				z-index:10;
				font-size: 45px;
				color: #fff;
				margin-top: -35px;
				cursor: pointer;
				opacity: 0.8;
			}
			.swiper-button-prev{
				left:234px;
			}
			.swiper-button-next{
				right: 2px;	
			}
			.swiper-button-prev:hover,
			.swiper-button-next:hover{
				background:#757678;
			}			
		}
		.home-hero-sub{
			width:1230px;
			height:171px;
			margin-top: 20px;
			.span4{
				height: 170px;
				width: 235px;
				float: left;
				.sspan{
					float: left;
					height: 85px;
					width: 78px;
					a{
						height: 85px;
						width:100%;
						img{
							height: 85px;
							width: 100%;
        					transition:all 0.1s linear 0s;
						}
						img:hover{
							box-shadow:0 10px 10px #000;
							transform: translate(0,-5px);
						}
					}
					
				}
			}
			.span16{
				height: 170px;
				width: 980px;
				float: right;
				ul{
					height: 170px;
					width: 100%;
					margin-top: 0px;
					padding-left: 0px;
					display: table;
					li{
						width: 316px;
						height: 170px;
						list-style: none;
						display: table-cell;
						padding-right: 15px;
					}
				}
				
			}
		}
	}
}
.page-main{
	width:100%;
	height: 3000px;
	background: #f5f5f5;
	.container{
		width:1230px;
		height: 1500px;
		margin:auto;
		.home-banner-box{
			height: 120px;
			width:1226px;

			a{
				display: block;
				height: 120px;
				width: 100%;
			}
		}
		.home-banner-box1{
			background: url(../assets/pictures/home-banner-box1.jpg)no-repeat;
		}
		.home-banner-box2{
			margin-top: 22px;
			background: url(../assets/home-brick-box2/home-banner-box2.jpg)no-repeat;
		}
		.home-banner-box3{
			margin-top: 22px;
			background: url(../assets/home-brick-box3/home-banner-box3.jpg)no-repeat;
		}		
	}
}
.fixed-box{
	height: 260px;
	width: 27px;
	background: #485;
	right: 5px;
	bottom: 80px;
	position: fixed;
	z-index: 31;
	dl{
		margin-top: 0px;
		dd{
			position: relative;
			height: 42px;
			width: 27px;
			background: #fff;
			margin-left: 0px;
			border:1px solid #f0f0f0;
		}
		.box-s{
			display: inline-block;
			height: 25px;
			width: 25px;
			margin:8px 3px;
		}
		.pict1{
			background: url(../assets/fix-box/firstb.png)no-repeat;
		}
		.pict2{
			background: url(../assets/fix-box/secondb.png)no-repeat;
		}
		.pict3{
			background: url(../assets/fix-box/thirdb.png)no-repeat;
		}
		.pict4{
			background: url(../assets/fix-box/fouthb.png)no-repeat;
		}
		.pict5{
			background: url(../assets/fix-box/fifthb.png)no-repeat;
		}
		.pict6{
			background: url(../assets/fix-box/totop.png)no-repeat;
			margin-top: 15px;
		}	
		.pict1:hover{
			background: url(../assets/fix-box/firsta.png)no-repeat;
		}
		.pict2:hover{
			background: url(../assets/fix-box/seconda.png)no-repeat;
		}
		.pict3:hover{
			background: url(../assets/fix-box/thirda.png)no-repeat;
		}
		.pict4:hover{
			background: url(../assets/fix-box/foutha.png)no-repeat;
		}
		.pict5:hover{
			background: url(../assets/fix-box/fiftha.png)no-repeat;
		}
		.pict6:hover{
			background: url(../assets/fix-box/totop_hover.png)no-repeat;
		}												
	}
	
}
</style>
<script>
import homeBrickBox from '../components/homeBrickBox'
import homeBrickBox2 from '../components/homeBrickBox2'
import headernav from '../components/header-nav'
import hiBox from '../components/hiBox'

export default {
  name: 'Home',
  components:{
  	homeBrickBox,
  	homeBrickBox2,
  	headernav,
  	hiBox,
  },
  data () {
    return {
      sites:[
      	{name:'小米商城'},
      	{name:'MIUI'},
      	{name:'IoT'},
      	{name:'云服务'},
      	{name:'金融'},
      	{name:'有品'},
      	{name:'企业团购'},
      	{name:'资质证书'},
      	{name:'协议规则'},
      	{name:'下载app'},
      	{name:'智能生活'},
      	{name:'Select Location'}],
      UserInfo:[
      	{name:'登录'},
      	{name:'注册'},
      	{name:'消息通知'}],
 
      dataList:[require("../assets/lbt/1.jpg"),require("../assets/lbt/2.jpg"),
      			require("../assets/lbt/3.jpg"),require("../assets/lbt/4.jpg"),
      			require("../assets/lbt/5.jpg"),require("../assets/lbt/6.jpg")],
      currentIndex:0,		//默认图片从第一张
      timer:null,			//定时器
      dataFromFather:[],
      site_category_list:[
      	{id:1 ,name:'手机 电话卡'},
      	{id:2 ,name:'电视 盒子'},
      	{id:3 ,name:'笔记本 显示器'},
      	{id:4 ,name:'家电 插线板'},
      	{id:5 ,name:'出行 穿戴'},
      	{id:6 ,name:'智能 路由器'},
      	{id:7 ,name:'电源 配件'},
      	{id:8 ,name:'健康 儿童'},
      	{id:9 ,name:'耳机 音响'},
      	{id:10,name:'生活 箱包'}],
      sspan4:[
      	{i:1,url:require('../assets/span4/ms.jpg')},
      	{i:2,url:require('../assets/span4/tg.jpg')},
      	{i:3,url:require('../assets/span4/td.jpg')},
      	{i:4,url:require('../assets/span4/mf.jpg')},
      	{i:5,url:require('../assets/span4/hx.jpg')},
      	{i:6,url:require('../assets/span4/cz.jpg')}] ,
      sspan16:[
      	{i:1,url:require('../assets/span16/left.jpg')},
      	{i:2,url:require('../assets/span16/middle.jpg')},
      	{i:3,url:require('../assets/span16/right.jpg')}],
      hBB1:[
      	{i:1, title:'小米10 至尊版',desc:'120X变焦/120W秒充/120Hz屏幕',price:'5299元起',
      		url:require('../assets/home-brick-box1/1.jpg'),},
      	{i:2, title:'Redmi K30 至尊版',desc:'120Hz弹出全屏幕，天玑1000+旗舰处...',price:'1999元起',
      		url:require('../assets/home-brick-box1/2.jpg'),},
      	{i:3, title:'腾讯黑鲨3S',desc:'骁龙865处理器，120Hz刷新率',price:'3999元起',
      		url:require('../assets/home-brick-box1/3.jpg'),},
      	{i:4, title:'Redmi 9A',desc:'5000mAh长循环大电量,6.53‘’超大护...',price:'599元起',
      		url:require('../assets/home-brick-box1/4.jpg'),},
      	{i:5, title:'小米10 青春版 5G',desc:'50倍潜望式变焦/轻薄5G手机',price:'1899元起',
      		url:require('../assets/home-brick-box1/5.jpg'),},
      	{i:6, title:'小米10',desc:'骁龙865/1亿像素相机',price:'3799元起',
      		url:require('../assets/home-brick-box1/6.jpg'),},
      	{i:7, title:'Redmi K30 Pro',desc:'双模5G，骁龙865，弹出全面屏',price:'2699元起',
      		url:require('../assets/home-brick-box1/7.jpg'),},
      	{i:8, title:'Redmi K30 Pro 变焦',desc:'双模5G，骁龙865，弹出全面屏',price:'3799元起',
      		url:require('../assets/home-brick-box1/8.jpg'),},],
      hBB2:[
      	{i:1, title:'Redmi红米电视',desc:'70英寸震撼巨大屏,4K画质,细腻如真',price:'3199元起',
      		url:require('../assets/home-brick-box2/r1.jpg'),},
      	{i:2, title:'小米全面屏电视E32C',desc:'全面屏设计，人工智能系统',price:'899元起',
      		url:require('../assets/home-brick-box2/r2.jpg'),},
      	{i:3, title:'小米全面屏电视E55A',desc:'全面屏设计，人工智能语音',price:'1999元起',
      		url:require('../assets/home-brick-box2/r3.jpg'),},
      	{i:4, title:'米家空调',desc:'出众噪音，快速制冷热',price:'1499元起',
      		url:require('../assets/home-brick-box2/r4.jpg'),},
      	{i:5, title:'米家互联网洗烘一体机 Pro 10kg',desc:'智能洗烘，省心省力',price:'2999元起',
      		url:require('../assets/home-brick-box2/r5.jpg'),},
      	{i:6, title:'Redmi全自动波轮洗衣机1A 8kg',desc:'一键操作，父母都爱用',price:'799元起',
      		url:require('../assets/home-brick-box2/r6.jpg'),},
      	{i:7, title:'15.6‘’四核i7 16G 独显 512G',desc:'全面均衡的国名轻薄本',price:'4899元起',
      		url:require('../assets/home-brick-box2/r7.jpg'),}],
      hBB3:[
      	{i:1, title:'小米电视4C 32英寸',desc:'高清液晶屏，人工智能系统',price:'899元起',
      		url:require('../assets/home-brick-box2/r1.jpg'),},
      	{i:2, title:'全面屏电视 55英寸E55X',desc:'潮流全面屏设计',price:'1999元起',
      		url:require('../assets/home-brick-box2/r2.jpg'),},
      	{i:3, title:'小米电视4A 70英寸',desc:'大屏更享受',price:'3499元起',
      		url:require('../assets/home-brick-box2/r3.jpg'),},
      	{i:4, title:'小米电视4C 43英寸',desc:'FHD全高清屏，钢琴烤漆',price:'1299元起',
      		url:require('../assets/home-brick-box2/r4.jpg'),},
      	{i:5, title:'小米电视4S 75英寸',desc:'4K HDR,人工智能语言',price:'4499元起',
      		url:require('../assets/home-brick-box2/r5.jpg'),},
      	{i:6, title:'小米全面屏电视65英寸 E65C',desc:'震撼大屏，时尚全面屏',price:'32999元起',
      		url:require('../assets/home-brick-box2/r6.jpg'),},
      	{i:7, title:'小米全面屏电视E32C',desc:'全面屏设计，人工智能系统',price:'899元起',
      		url:require('../assets/home-brick-box2/r7.jpg'),}],


    }
  },
  methods:{
  	showhidediv(){
  		this.$refs.content.style.background="#fff"
  		this.$refs.content.firstElementChild.style.color="#fe5038"
		this.$refs.menu.style.display="block"
	},
	removeActive(){
  		this.$refs.content.style.background="#333333"
  		this.$refs.content.firstElementChild.style.color="#b0b0b0"
		this.$refs.menu.style.display="none"
	},
	gotoPage(index){
  		this.currentIndex=index;
  	},
  	triggerBrotherMethods(){
  		this.$refs.brother.bortherMethods()
  	},
  	triggerBrotherMethods2(){
  		this.$refs.brother.bortherMethods2()
  	},
  	
},
  computed:{
  	prevIndex(){
  		if(this.currentIndex==0){
  			return this.dataList.length - 1;
  		}else{
  			return this.currentIndex - 1;
  		}
  	},
  	nextIndex(){
  		if(this.currentIndex==this.dataList.length - 1){
  			return 0;
  		}else{
  			return this.currentIndex + 1;
  		}
  	},
  	runInv() {
  		this.timer = setInterval(() => {
    	this.gotoPage(this.nextIndex)
  		}, 5000)
	},
	clearInv (){
        clearInterval(this.invId)
    }
  },
  mounted(){
  		this.runInv()
  }
  	
}
</script>