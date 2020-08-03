<template>
	<div class="tab-controller">
		<div class="tab-controller-item" v-for="(item,index) in titles" :key="item" @click="itemClick(index)">
			<span :class="{active:index===currenindex}">{{item}}</span>
		</div>
	</div>
</template>

<script>
	export default{
		name:'TabCotroller',
		props:{
			titles:{
				type:Array,
				default(){
					return []
				}
			}
		},
		data(){
			return{
				currenindex:0
			}
		},
		methods:{
			itemClick(index){
				this.currenindex = index
				this.$emit("tabClick",index)
			}
		}
	}
</script>

<style>
	.tab-controller{
		display: flex;
		text-align: center;
		height: 40px;
		line-height: 40px;
		font-size: 15px;
		background-color: #fff;
		border-top: 1px solid #eee;
		border-bottom: 1px solid #eee;
	}
	
	.tab-controller-item{
		flex: 1;
	}
	
	.active{
		color: var(--color-high-text);
		border-bottom: 3px solid var(--color-tint);
		padding: 5px;
	}
</style>
