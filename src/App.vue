<template>
	<div id="app">
		<router-view />
	</div>
</template>

<style lang="scss">
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	li {
		list-style: none;
	}
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
	}
	html,
	body {
		height: 100vh;
	}
	body {
		background: #0f3854;
		background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 70%);
		background-size: 100%;
	}
</style>
