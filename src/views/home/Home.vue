<template>
	<div id="home">
		<nav-bar class="homenavbar">
			<div slot="center">
				购物街
			</div>
		</nav-bar>
		<scroll class="content" ref="scroll">
			<home-swiper :banners="banners"/>
			<home-recommand-view :recommend="recommend"/>
			<home-feature/>
			<tab-controller :titles="['流行','新款','精选']" class="tab-controller" @tabClick="tabClick"/>
			<goods-list :goodsList="goodsShow"/>
		</scroll>
		<back-top class="backTop" @click.native="backTopClick"/>
	</div>
</template>

<script>
	
	import HomeSwiper from './childcomps/HomeSwiper.vue'
	import HomeRecommandView from './childcomps/HomeRecommandView.vue'
	import HomeFeature from './childcomps/HomeFeature.vue'
	
	import NavBar from 'components/common/navbar/NavBar.vue'
	import TabController from 'components/content/tabController/TabController.vue'
	import GoodsList from 'components/content/goodsList/GoodsList.vue'
	import Scroll from 'components/common/scroll/Scroll.vue'
	import BackTop from 'components/content/backtop/BackTop.vue'
	
	import {getHomeMultidata,getHomeGoods} from 'network/home.js'
	
	export default{
		name:'Home',
		components:{
			HomeSwiper,
			HomeRecommandView,
			HomeFeature,
			NavBar,
			TabController,
			GoodsList,
			Scroll,
			BackTop
		},
		data(){
			return {
				banners:[],
				recommend:[],
				goodsList:{
					'pop':{page:0,list:[]},
					'new':{page:0,list:[]},
					'sell':{page:0,list:[]}
				},
				currentIndex:'pop'
			}
		},
		created() {
			this.getHomeMultidata(),
			this.getHomeGoods('pop'),
			this.getHomeGoods('new'),
			this.getHomeGoods('sell')
		},
		computed:{
			goodsShow(){
				return this.goodsList[this.currentIndex].list
			}
		},
		methods:{
			/*
			 *点击时间
			 */
			tabClick(index){
				switch(index){
					case 0 : 
						this.currentIndex = 'pop'
						break
					case 1 :
						this.currentIndex = 'new'
						break
					case 2 :
						this.currentIndex = 'sell'
						break		
					
				}
			},
			backTopClick(){
				this.$refs.scroll.scrollTo(0,0,300)
			},
			/* 
			 *网络数据请求相关方法
			 */
			getHomeMultidata(){
				getHomeMultidata().then(res => {
					console.log(res.data.data)
					this.banners = res.data.data.banner.list
					this.recommend = res.data.data.recommend.list
				})
			},
			getHomeGoods(type){
				const page = this.goodsList[type].page + 1
				getHomeGoods(type,page).then(res => {
					this.goodsList[type].list.push(...res.data.data.list)
					this.goodsList[type].page +=1
				})
			}
		}
	}
</script>

<style scoped>
	#home{
		position: relative;
		height: 100vh;
	}
	.homenavbar{
		background-color: var(--color-tint);
		color: white;
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 9;
	}
	/* .tab-controller{
		position: sticky;
		top: 44px;
	} */
	.content{
		position: absolute;
		right: 0;
		left: 0;
		top: 44px;
		bottom: 49px;
	}
	.backTop{
		position: fixed;
		right: 10px;
		bottom: 50px;
	}
</style>
