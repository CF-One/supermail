<template>
	<div class="content">
		<ul>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
			<li>1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
			<li>5</li>
		</ul>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	export default{
		name:'Category',
		data(){
			return{
				bscorll:null
			}
		},
		/*
		*probeType
		* 0和1：不监听内容滚动
		* 2：监听鼠标滑动的滚动，不监听回弹滚动
		* 3：监听所有滚动
		*/
		mounted() {
			this.bscorll = new BScroll('.content',{
				probeType:3,
				pullUpLoad:true
			}),
			// this.bscorll.on("scroll",(posit) => {
			// 	console.log(position)
			// }),
			/*
			*默认情况下只调用一次
			* 调用finishPullUp方法可多次调用
			*/
			this.bscorll.on("pullingUp",() => {
				console.log("上拉加载更多")
				this.bscorll.finishPullUp()
			})
		}
	}
</script>

<style scoped>
	.content{
		height: 300px;
		background-color: #EEEEEE;
		overflow: hidden;
	}
</style>
