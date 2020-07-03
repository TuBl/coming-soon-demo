<template>
	<div class="grid-container">
		<div class="header">
			<Header></Header>
		</div>
		<div class="main">
			<div class="main--clock-container">
				<h1>Be Ready We Will Start Soon...</h1>
				<Clock></Clock>
				<h1>Leave us your Email here to let you know when we start..</h1>
			</div>
			<form @submit="onSubmit" class="main--form">
				<div class="email">
					<label for="email">Email</label>
					<input type="email" v-model="email" name="email" />
				</div>

				<div class="btn">
					<input type="submit" value="Subscribe" />
				</div>
			</form>
			<div class="main--secondary-container">
				<h1>Take a look here for the second clock.</h1>
				<div class="btn">
					<input type="submit" value="Second Time" />
				</div>
				<div class="img-container">
					<img src="../assets/temp_head.jpeg" alt="" />
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import Clock from "@/components/Clock.vue";
	import Header from "@/components/Header.vue";
	export default {
		name: "Home",
		data() {
			return {
				email: "",
			};
		},
		components: {
			Clock,
			Header,
		},
	};
</script>

<style lang="scss" scoped>
	label {
		color: #586f7c;
		font-size: 1.2em;
		padding: 1em;
		font-family: Verdana, Geneva, Tahoma, sans-serif;
	}

	input[type="email"] {
		padding: 1.2em;
		font-size: 1em;
		background: #f5f5ed;
		color: #586f7c;
		border: outset #586f7c;
		box-shadow: 10px 10px 10px #586f7c;
		width: 50%;
	}
	input:focus {
		background: #fffffc;
	}
	.grid-container {
		display: grid;
		color: #fffffc;
		gap: 5em;
		grid-template-columns: 0.2fr 1fr 0.2fr;
		grid-template-rows: 200px 1fr 40px;
		grid-template-areas:
			"header   header    header"
			"main     main      main"
			"footer   footer    footer";

		.header {
			grid-area: header;
			padding: 1em;
			height: 100%;
			width: 100%;
		}
		.main {
			grid-area: main;
			height: 100%;
			width: 100%;
			padding: 1em;
			display: flex;
			flex-direction: column;
			.main--clock-container {
				margin-bottom: 2em;
				h1 {
					margin-bottom: 1em;
				}
				h1:nth-of-type(2) {
					margin-top: 1em;
				}
			}
			form {
				display: grid;
				margin-bottom: 10em;
				grid-template-columns: 1fr;
				gap: 1em;
				grid-template-rows: 1fr 1fr;
				grid-template-areas:
					"email"
					"btn";

				.email {
					grid-area: email;
					height: 100%;
					width: 100%;
				}
				.btn {
					grid-area: btn;
					height: 100%;
					width: 100%;
					margin-top: 1em;
					display: flex;
					justify-content: center;
					text-align: center;

					input {
						background: #586f7c;
						color: #fffffc;
						padding: 1em;
						margin-left: 5em;
						font-size: 1em;
						width: 45%;
						border-radius: 3%;
					}
				}
			}
			.main--secondary-container {
				height: 100%;
				width: 100%;
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				text-align: center;
				.btn {
					height: 4em;
					width: 100%;
					margin-top: 1em;
					display: flex;
					justify-content: center;
					text-align: center;
					margin-bottom: 5em;

					input {
						background: #586f7c;
						color: #fffffc;

						font-size: 1em;
						width: 25%;
						border-radius: 3%;
					}
				}
				.img-container {
					height: 515px;
					widows: 960px;
				}
				img {
					height: 100%;
					width: 60%;
					box-shadow: 0px 0px 10px rgba(10, 175, 230, 1);
				}
			}
		}
	}
</style>
