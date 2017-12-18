<template>
  <div>
    <header class="header">
    	<div class="back iconfont">&#xe607;</div>
    	<div class="search"></div>
    	<div class="city">城市</div> 
    </header>

    <swiper :options="swiperOption">
	    <swiper-slide v-for="item in swiperInfo" :key="item.id">
        <div class="swiper-img-con">
          <img class="swiper-img" :src="'../../../static/image/'+item.imgUrl+''"/>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>

    <swiper :options="iconOption">
      <swiper-slide v-for="(pageInfo, index) in pages" :key="index">
        <div class="icon-wrapper">
          <div v-for="item in pageInfo" :key="item.id" class="icon-item">
            <a href="javascript:;">
              <div class="icon-img-con">
                <img class="icon-img" :src="'../../../static/image/'+item.imgUrl+''"/>
              </div>
              <div class="icon-text">{{item.text}}</div>
            </a>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    
    <main>
      <ul class="listUl1">
        <li class="listUl1Item">
          <span class="iconfont">&#xe68b;定位失败</span>
        </li>
        <li class="listUl1Item">
          <span class="iconfont">&#xe679;5折泡温泉</span>
        </li>
      </ul>

      <ul class="listUl2">
        <li class="listUl2Item" v-for="item in list1info">
          <div class="listText">
            <p class="listTit">{{item.tit}}</p>
            <p class="listDes">{{item.des}}</p>
          </div>
          <div class="listImgCon">
            <img class="listImg" :src="'../../../static/image/'+item.imgUrl+''">
          </div>
        </li>
        <li class="listUl2Item" v-for="item in list2info">
          <div class="listText">
            <p class="listTit">{{item.tit}}</p>
            <p class="listDes">{{item.des}}</p>
          </div>
          <div class="listImgCon">
            <img class="listImg" :src="'../../../static/image/'+item.imgUrl+''">
          </div>
        </li>
      </ul>
     
      <div class="hotSight">
        <h2 class="hotsight-h2">热销推荐</h2>
        <div class="hotsight-con">
          <ul class="hotsight-ul">
            <li class="hotsight-li" v-for="item in hotsightInfo" :key="item.id">
              <div class="hotsight-img-con">
                <img class="hotsight-img" :src="'../../../static/image/'+item.imgUrl+''">
              </div>
              <div class="hotsight-info">
                <div class="hotsight-tit">{{item.tit}}</div>
                <div class="hotsight-des">{{item.des}}</div>
                <p class="hotsight-price">￥<em class="hotsight-priceNum">{{item.price}}</em><span class="hotsight-priceTit">起</span>
                </p>
              </div>
            </li>
          </ul>
          <div class="moreSight">
            <a class="moreSightLink" href="javascript:;">查看所有产品</a>
          </div>
        </div>
      </div>

      <div class="weekend">
        <h2 class="weekend-h2">周末去哪儿</h2>
        <div class="weekend-con">
          <div class="weekend-item" v-for="item in weekendInfo" :key="item.id">
            <div class="weekend-img-con">
              <img class="weekend-img" :src="'../../../static/image/'+item.imgUrl+''">
            </div>
            <div class="weekend-info">
              <p class="weekend-tit">{{item.tit}}</p>
              <p class="weekend-des">{{item.des}}</p>
            </div>
          </div>
        </div>
      </div>
      
      <div class="price-desc">
        <span class="price-desc-icon iconfont">&#xe837;</span>
        <div class="price-desc-info"><span class="price-desc-tit">票面价</span>是指通过景区指定窗口售卖的纸质门票上标注的价格</div>
      </div>
    </main>
    
    <div class="footer">
      <div class="nav">
        <ul class="navList">
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">机票</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">酒店</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">公寓</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">团购</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">火车票</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">景点</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">接送机</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">度假</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">攻略</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">旅途</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">车车</span>
            </a>
          </li>
          <li>
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">当地人</span>
            </a>
          </li>
          <li class="tag">
            <a href="javascript:;">
              <div class="icon"></div>
              <span class="nav-tit">更多</span>
            </a>
          </li>
        </ul>
      </div>

      <ul class="myNav">
        <li>
          <a href="javascript:;">登录</a>
        </li>
        <li>
          <a href="javascript:;">我的订单</a>
        </li>
        <li style="display: none;">
          <a href="javascript:;">个人中心</a>
        </li>
        <li>
          <a href="javascript:;">最近浏览</a>
        </li>
        <li>
          <a href="javascript:;">关于我们</a>
        </li>
      </ul>
      
      <ul class="mobile_pc">
        <li>
          <a href="javascript:;">触屏版</a>
        </li>
        <li>
          <a href="javascript:;">电脑版</a>
        </li>
      </ul>

      <div class="copyRight">
        <span>Qunar 京ICP备05021087</span>
        <a href="javascript:;">意见反馈</a>
      </div>
    </div>

  </div>
</template> 

<script>
  export default {

    name: 'Index',

    data () {
      return {
        swiperInfo: [],
        iconInfo: [],
        list1info: [],
        list2info: [],
        hotsightInfo: [],
        weekendInfo: [],
        navInfo: [],
        swiperOption: {
          autoplay: 3000,
          pagination: '.swiper-pagination',
          loop: true
        },
        iconOption: {
          pagination: '.swiper-pagination'
        }
      }
    },

    computed: {
      pages () {
        const pages = []
        this.iconInfo.forEach((value, index) => {
          let page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(value)
        })
        return pages
      }
    },

    methods: {

      getIndexData () {
        this.$http.get('/static/index.json')
          .then(this.handleGetDataSucc.bind(this))
      },

      handleGetDataSucc (res) {
        const body = res.body
        if (body && body.data && body.data.swiper) {
          this.swiperInfo = body.data.swiper
          this.iconInfo = body.data.icons
          this.list1info = body.data.list1
          this.list2info = body.data.list2
          this.hotsightInfo = body.data.hotsight
          this.weekendInfo = body.data.weekend
          this.navInfo = body.data.nav
        }
      }
    },

    created () {
      this.getIndexData()
    }

  }
</script>

<style scoped>
	.header {
		display: flex;
		background: #05bad5;
		color: #fff;
	}
	.back {
		width: .64rem;
		line-height: .86rem;
		text-align: center;
	}
	.search {
		flex: 1;
		margin: .14rem .18rem;
		background: #fff;
		border-radius: .1rem;
	}
	.city { 
		width: 1.14rem;
		line-height: .86rem;
		text-align: center;
	}
	.swiper-img-con {
		overflow: hidden;
		width: 100%;
		height: 0;
		padding-bottom: 31.25%;
	}
	.swiper-img {
		width: 100%;
	}
  .icon-wrapper {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: .35rem;
  }
  .icon-item {
    box-sizing: border-box;
/*    float: left;*/
    width: 25%;
    padding: .4rem;
  }
  .icon-img-con {
    width: 100%;
    height: 0;
    padding-bottom: 100%;
  }
  .icon-img {
    width: 100%;
  }
  .icon-text {
    margin-top: .2rem;
    font-size: .26rem;
    color: #212121;
    text-align: center;
  }
  main {
    background: #f5f5f5;
  }
  .listUl1{
    width: 100%;
    height: 0.97rem;
    position: relative;
  }
  .listUl1::before{
    content: "";
    width: 100%;
    height: 1px;
    background: #e1e1e1;
    position: absolute;
    top: 0;
    transform: scaleY(0.5);
    transform-origin: left bottom;
  }
  .listUl1Item {
    width: 50%;
    height: 0.97rem;
    background: #fff;
    float: left;
    text-align: center;
    font-size: 0.25rem;
    line-height: 0.97rem;
    position: relative;
  }
  .listUl1Item:first-child::before {
    content: "";
    width: 1px;
    height: 100%;
    background: #e1e1e1;
    position: absolute;
    right: 0;
    transform: scaleX(0.5);
    transform-origin: left bottom;
  }
  .listUl2 {
    width: 100%;
    height: 1.4rem;
    margin-top: 0.2rem;
    position: relative;
  }
  .listUl2::before{
    content:"";
    width:100%;
    height:1px;
    background:#e1e1e1;
    position:absolute;
    top:0;
    transform:scaleY(0.5);
    transform-origin:left bottom;
  }
  .listUl2::after{
    content:"";
    width:100%;
    height:1px;
    background:#e1e1e1;
    position:absolute;
    top:0;
    transform:scaleY(0.5);
    transform-origin:left bottom;
  }
  .listUl2Item {
    width: 50%;
    height: 1.4rem;
    background: #fff;
    float:left;
    box-sizing: border-box;
    padding-left: .48rem;
    position: relative;
  }
  .listUl2Item:first-child::before {
    content: "";
    width: 1px;
    height: 100%;
    background: #e1e1e1;
    position: absolute;
    right: 0;
    transform: scaleX(0.5);
    transform-origin: left bottom;
  }
  .listText {
    height: .65rem;
    float: left;
    margin-top: .35rem;
  }
  .listTit {
    width: 1.1rem;
    font-size: .24rem;
    color: #ff3738;
    margin-bottom: .2rem;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .listDes {
    width: 1.1rem;
    font-size: .18rem;
    color: #525252;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .listImgCon {
    width: 1.31rem;
    height: .98rem;
    float: left;
    margin-left: .55rem;
    margin-top: .2rem;
  }
  .listImg {
    width: 100%;
  }
  .hotsight-h2 {
    height: .8rem;
    padding-left: .26rem;
    line-height: .8rem;
    color: #212121;
  }
  .hotsight-con {
    background: #fff;
  }
  .hotsight-li {
    position: relative;
    overflow: hidden;
    height: 1.4rem;
    padding: .24rem;
    display: flex;
  }
  .hotsight-li::before {
    content:"";
    width:100%;
    height:1px;
    background:#e1e1e1;
    position:absolute;
    bottom:0;
    transform:scaleY(0.5);
    transform-origin:left bottom;
  }
  .hotsight-img-con {
    width: 1.4rem;
    height: 1.4rem;
  }
  .hotsight-img {
    width: 100%;
  }
  .hotsight-info {
    margin-left: 0.2rem;
  }
  .hotsight-tit {
    overflow: hidden;
    margin-top: .04rem;
    margin-bottom: .1rem;
    color: #212121;
    font-size: .3rem;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .hotsight-des {
    overflow: hidden;
    margin-bottom: .1rem;
    height: .4rem;
    line-height: .4rem;
    color: #9e9e9e;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .hotsight-price {
    font-size: .24rem;
    color: #ff8300;
  }
  .hotsight-priceNum {
    font-size: .36rem;
    padding: 0 .04rem;
  }
  .hotsight-priceTit {
    color: #9e9e9e;
    font-size: .24rem;
  }
  .moreSight {
    width: 100%;
    height: .88rem;
    color: #00afc7;
    line-height: .88rem;
    text-align: center;
  }
  .moreSightLink {
    display: block;
    line-height: .88rem;
  }
  .weekend-h2 {
    height: .8rem;
    padding-left: .26rem;
    line-height: .8rem;
    color: #212121;
  }
  .weekend-item {
    margin-bottom: .1rem;
    background: #fff;
  }
  .weekend-img-con {
    overflow: hidden;
    height: 0;
    padding-bottom: 37.4375%;
  }
  .weekend-img {
    width: 100%;
  }
  .weekend-info {
    padding: .14rem .2rem .2rem .2rem;
  }
  .weekend-tit {
    overflow: hidden;
    padding-right: 1.4rem;
    color: #212121;
    font-size: .28rem;
    line-height: .48rem;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .weekend-des {
    overflow: hidden;
    padding-right: 1.4rem;
    color: #616161;
    font-size: .24rem;
    line-height: .42rem;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
  .price-desc {
    margin-top: .1rem;
    padding: .14rem .1rem;
    font-size: .24rem;
    line-height: .32rem;
    background: #fff;
    color: #616161;
  }
  .price-desc-icon {
    width: .24rem;
    display: block;
    float: left;
    line-height: .32rem;
  }
  .price-desc-info {
    display: inline;
    margin-left: .2rem;
  }
  .price-desc-tit {
    font-weight: bold;
  }
  .footer {
    background: #f3f3f3;
  }
  .nav {
    font-size: .28rem;
  }
  .navList {
    width: 6rem;
    margin: 0 auto;
    padding: .2rem .2rem 0 .2rem;
    overflow: hidden;
    position: relative;
  }
  .navList>li {
    margin: 0px;
    padding-left: .2rem;
    height: .62rem;
    width: 1.3rem;
    float: left;
    position: relative;
    background: none;
  }
  .navList>li>a {
    display: block;
    height: .44rem;
    width: 100%;
    font-size: .24rem;
  }
  .navList>li>a>div {
    float: left;
    width: .44rem;
    height: .44rem;
    background: url("../../../static/image/nav_icon.png");
    background-size: 3.5rem 1rem;
  }
  .nav-tit {
    float: left;
    display: inline-block;
    color: #9e9e9e;
    margin: 0.015rem 0 0 0.025rem;
    border-bottom: 1px solid #acacac;
    font-size: 0.12rem;
  }
  .navList>.tag {
    position: absolute;
    right: 6px;
    background: #f3f3f3;
    font-size: 14px;
    color: #9e9e9e;
    width: 70px;
  }
  .myNav {
    width: 100%;
    height: 0.78rem;
    border-bottom: 1px solid #cacaca;
    display: flex;
  }
  .myNav>li {
    /*float: left;*/
    padding-left: 0.4rem;
  }
  .myNav>li>a {
    position: relative;
    color: #25a4bb;
    font-size: 14px;
    line-height: 39px;
  }
  .mobile_pc {
    padding: 0.2rem 0 0 0;
    text-align: center;
  }
  .mobile_pc>li {
    display: inline-block;
    margin: 0  0.3rem;
  }
  .copyRight {
    color: #9e9e9e;
    text-align: center;
    font-size: 0.28rem;
    padding: 0.2rem;
  }
</style>
