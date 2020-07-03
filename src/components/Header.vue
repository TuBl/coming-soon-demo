<template>
	<nav class="grid-container">
		<div class="nav--main">Page 1</div>
		<div class="nav--image">
			<img src="../assets/xd.webp" alt="" />
		</div>
		<ul class="nav-list">
			<li>Home</li>
			<li>About</li>
			<li>Contact us</li>
		</ul>
	</nav>
</template>

<script>
	export default {
		name: "Header",
	};
</script>

<style lang="scss" scoped>
	img {
		height: 100%;
		width: 50%;
	}
	.grid-container {
		display: grid;
		grid-template-rows: 1fr;
		grid-template-columns: 0.2fr 1fr 0.4fr;
		color: #fffffc;

		li {
			cursor: pointer;
		}
		li:hover {
			color: rgba(10, 175, 230, 1);
		}
	}
</style>
