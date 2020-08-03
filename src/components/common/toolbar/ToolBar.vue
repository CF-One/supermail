<template>
	<div class="toolBar">
		<slot></slot>
	</div>
</template>

<script>
	export default{
		name:'ToolBar'
	}
</script>

<style>
	.toolBar{
		width: 100%;
		height: 49px;
		display: flex;
		background-color: #F2F2F2;		
		left: 0;
		bottom: 0;
		position: fixed;
		box-shadow: 0px -2px 6px #E2E2E2;
	}
</style>
