<template>
  <div id="app">
	<router-view></router-view>
    <main-tool-bar></main-tool-bar>
  </div>
</template>

<script>
	import MainToolBar from 'components/content/maintoolbar/MainToolBar.vue'
	export default {
		name: 'App',
		components: {
			MainToolBar
		}
	}
</script>

<style>
@import url('assets/css/base.css');
</style>
