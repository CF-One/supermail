<template>
	<div class="toolBarItem" @click="itemClick">
		<div v-if="isActive">
			<slot name="item-icon">
				<img src="~assets/imgs/tabbar/home.png" />
			</slot>			
		</div>
		<div v-else>
			<slot name="item-icon-active">
				<img src="~assets/imgs/tabbar/home.png" />
			</slot>	
		</div>
		<div :style="activeStyle">
			<slot name="item-name">首页</slot>
		</div>		
	</div>
</template>

<script>
	export default{
		name:'ToolBarItem',
		props:{
			path:{
				type:String
			},
			activeColor:{
				type:String,
				default:"red"
			}
		},
		data(){
			return{
				//isActive:false
			}
		},
		computed:{
			isActive(){
				return this.$route.path.indexOf(this.path)
				
			},
			activeStyle(){
				return this.isActive ? {} : {color:this.activeColor}
			}
		},
		methods:{
			itemClick(){
				this.$router.push(this.path)
			}
		}
	}
</script>

<style>
	.toolBarItem{
		text-align: center;
		flex-grow: 1;
		margin-top: 3px;
	}
	.toolBarItem img{
		width: 24px;
		margin-bottom: -5px;
	}
	.active{
		color: red;
	}
</style>
