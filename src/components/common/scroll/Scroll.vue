<template>
	<div class="scroll" ref="scroll">
		<div class="content" >
			<slot></slot>
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	export default{
		name:'Scroll',
		data(){
			return{
				bscorll:null,
				message:"陈大大"
			}
		},
		mounted() {
			this.bscorll = new BScroll(this.$refs.scroll,{
				
			})
		},
		methods:{
			scrollTo(x,y,time){
				this.bscorll.scrollTo(x,y,time)
			}
		}
	}
</script>

<style scoped>
</style>
