<template>
	<div id="maintoolbar">
		<tool-bar>
			<tool-bar-item path="/home">
				<img src="~assets/imgs/tabbar/home.png" slot="item-icon"/>
				<img src="~assets/imgs/tabbar/home-active.png" slot="item-icon-active"/>
				<span slot="item-name">首页</span>
			</tool-bar-item>
			<tool-bar-item path="/category">
				<img src="~assets/imgs/tabbar/category.png" slot="item-icon"/>
				<img src="~assets/imgs/tabbar/category-active.png" slot="item-icon-active"/>
				<span slot="item-name">分类</span>
			</tool-bar-item>
			<tool-bar-item path="/cart">
				<img src="~assets/imgs/tabbar/cart.png" slot="item-icon"/>
				<img src="~assets/imgs/tabbar/cart-active.png" slot="item-icon-active"/>
				<span slot="item-name">购物车</span>
			</tool-bar-item>
			<tool-bar-item path="/profile">
				<img src="~assets/imgs/tabbar/profile.png" slot="item-icon"/>
				<img src="~assets/imgs/tabbar/profile-active.png" slot="item-icon-active"/>
				<span slot="item-name">我的</span>
			</tool-bar-item>
		</tool-bar>
	</div>
</template>

<script>
	import ToolBar from 'components/common/toolbar/ToolBar.vue'
	import ToolBarItem from 'components/common/toolbar/ToolBarItem.vue'
	export default{
		name:'MainToolBar',
		components:{
			ToolBar,
			ToolBarItem
		}
	}
</script>

<style>
</style>
