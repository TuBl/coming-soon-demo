<template>
	<nav class="grid-container">
		<div class="nav--main">Page 1</div>
		<div class="nav--image">
			<img src="../assets/xd.webp" alt="" />
		</div>
		<ul class="nav-list">
			<li>INFORMATION</li>
			<li>QUESTION AND ANSWER</li>
			<li>CONTACTS</li>
			<li>SECOND PAGE</li>
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
		li:nth-child(1) {
			font-size: 1em;
		}
		li:nth-child(2) {
			font-size: 0.9em;
			width: 90%;
			margin-left: 1em;
		}
		li:nth-child(3) {
			font-size: 0.8em;
			width: 80%;
			margin-left: 2em;
		}
		li:nth-child(4) {
			font-size: 0.7em;
			width: 70%;
			margin-left: 3.4em;
		}
		li {
			cursor: pointer;
			padding: 1em;
			margin-bottom: 1em;
			border: outset;
		}
		li:hover {
			color: rgba(10, 175, 230, 1);
			transform: scale(0.98);
		}
	}
</style>
