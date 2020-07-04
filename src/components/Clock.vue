<template>
	<div class="clock">
		<countdown
			:time="120 * 24 * 60 * 60 * 1000"
			ref="countdown"
			:auto-start="false"
		>
			<template slot-scope="props">
				<ul class="time">
					<li>
						<span>Days</span> <span>{{ props.days }}</span>
					</li>
					<li>
						<span>Hours</span> <span>{{ props.hours }}</span>
					</li>
					<li>
						<span>Minutes</span> <span>{{ props.minutes }}</span>
					</li>
					<li>
						<span>Seconds</span> <span>{{ props.seconds }}</span>
					</li>
				</ul>
			</template>
		</countdown>
		<!-- <p class="time">{{ time }}</p>
		<p class="date">{{ date }}</p> -->
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
				format: "",
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
			// this.interval = setInterval(() => this.updateTime(), 1000);
			// this.updateTime();
			this.$refs.countdown.start();
		},
		mounted() {
			this.$refs.countdown.start();
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
			font-size: 2em;
			padding: 5px 0;
			display: flex;
			justify-content: center;
			align-items: center;
			text-align: center;
			li {
				border: outset;
				display: flex;
				flex-direction: column;
			}
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
