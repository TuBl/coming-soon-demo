<template>
	<div class="clock">
		<p class="time">{{ time }}</p>
		<p class="date">{{ date }}</p>
	</div>
</template>

<script>
	export default {
		name: "Clock",
		data() {
			return {
				time: "",
				date: "",
				week: ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"],
				interval: null,
			};
		},
		methods: {
			updateTime() {
				let cd = new Date();
				this.time = `${this.zeroPadding(cd.getHours(), 2)} : ${this.zeroPadding(
					cd.getMinutes(),
					2
				)} : ${this.zeroPadding(cd.getSeconds(), 2)}`;

				this.date = `${this.zeroPadding(
					cd.getFullYear(),
					4
				)} - ${this.zeroPadding(cd.getMonth() + 1, 2)} - ${this.zeroPadding(
					cd.getDate(),
					2
				)}  ${this.week[cd.getDay()]}`;
			},
			zeroPadding(num, digit) {
				let zero = "";
				for (let i = 0; i < digit; i++) {
					zero += "0";
				}
				return (zero + num).slice(-digit);
			},
		},
		created() {
			this.interval = setInterval(() => this.updateTime(), 1000);
			this.updateTime();
		},
	};
</script>

<style lang="scss" scoped>
	p {
		margin: 0;
		padding: 0;
	}
	.clock {
		font-family: "Share Tech Mono", monospace;
		color: #ffffff;
		color: #daf6ff;
		text-shadow: 0 0 20px rgba(10, 175, 230, 1), 0 0 20px rgba(10, 175, 230, 0);
		.time {
			letter-spacing: 0.05em;
			font-size: 80px;
			padding: 5px 0;
		}
		.date {
			letter-spacing: 0.1em;
			font-size: 24px;
		}
		.text {
			letter-spacing: 0.1em;
			font-size: 12px;
			padding: 20px 0 0;
		}
	}
</style>
