<template>
	<div class="goodsList">
		<goods-list-item v-for="(item,index) in goodsList" :key='index' :goods='item'/>
	</div>
</template>

<script>
	import GoodsListItem from './GoodsListItem.vue'
	export default{
		name:'GoodsList',
		components:{
			GoodsListItem
		},
		props:{
			goodsList:{
				type:Array,
				default(){
					return []
				}
			}
		}
	}
</script>

<style>
	.goodsList{
		display: flex;
		flex-wrap: wrap;
		justify-content:center;
	}
</style>
