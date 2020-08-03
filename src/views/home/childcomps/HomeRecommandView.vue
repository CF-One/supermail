<template>
	<div class="HomeRecommandView">
		<div class="RecommandItem" v-for="item in recommend" :key='item.sort'>
			<a :href="item.link">
				<img :src="item.image" />
				<p>{{item.title}}</p>
			</a>			
		</div>
	</div>
</template>

<script>
	export default {
		name:'HomeRecommandView',
		props:{
			recommend:{
				type:Array,
				default(){
					return []
				}
			}
		}
	}
</script>

<style>
	.HomeRecommandView{
		display: flex;
		text-align: center;
		padding: 14px 0 20px 0;
		border-bottom: 10px solid #eee;
	}
	.RecommandItem{
		flex:1;
	}
	.RecommandItem img{
		width: 60px;
		height: 60px;
		margin-bottom: 8px;
	}
</style>
