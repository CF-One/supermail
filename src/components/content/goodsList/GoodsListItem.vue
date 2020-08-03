<template>
	<div class="goodsListItem">
		<img :src="goods.show.img" />
		<div class="goodsInfo">
			<p>{{goods.title}}</p>
			<span class="price">￥{{goods.price}}</span>
			<span class="collect">{{goods.cfav}}</span>
		</div>
	</div>
</template>

<script>
	export default{
		name:'GoodsListItem',
		props:{
			goods:{
				type:Object,
				default(){
					return {}
				}
			}
		}
	}
</script>

<style>
	.goodsListItem{
		width: 48%;
		padding: 5px;
	}
	.goodsListItem img{
		width: 100%;
		border-radius: 7px;
	}
	.goodsInfo{
		text-align: center;
	}
	.goodsInfo p{
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
		margin-bottom: 3px;
	}
	.price{
		color: var(--color-high-text);
		margin-right: 17px;
	}
	.collect{
		position: relative;
	}
	.collect::before{
		content: '';
		position: absolute;
		left: -15px;
		width: 14px;
		height: 14px;
		background: url(~assets/imgs/common/collect.svg) 0 0/14px 14px;
	}
</style>
