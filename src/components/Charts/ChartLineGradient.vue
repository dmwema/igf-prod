<template>
	<div>
		<!-- Gradient Line chart -->
		<canvas ref="chart" class="chart-line-gradient" :style="{'height': height + 'px'}"></canvas>
		<!-- Gradient Line chart -->
	</div>
</template>

<script>
	import { Chart, registerables } from 'chart.js';
	Chart.register(...registerables);

	export default ({
		props: [
		],
		data(){
			return {
				height: 300,
			} ;
		},
		mounted () { 
    		let ctx = this.$refs.chart.getContext("2d");

			var gradientStroke1 = ctx.createLinearGradient(0, 230, 0, 50);

			gradientStroke1.addColorStop(1, 'rgba(24, 144, 255, .3)');
			gradientStroke1.addColorStop(0.2, 'rgba(24, 144, 255, 0)');
			gradientStroke1.addColorStop(0, 'rgba(24, 144, 255, 0)'); // Primary color

			var gradientStroke2 = ctx.createLinearGradient(0, 230, 0, 50);

			gradientStroke2.addColorStop(1, 'rgba(20,20,20,0.3)');
			gradientStroke2.addColorStop(0.2, 'rgba(20,20,20,0)');
			gradientStroke2.addColorStop(0, 'rgba(20,20,20,0)'); // Dark color

			this.chart = new Chart(ctx, {
				type: "line",
				data: {
					labels: ["Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
					datasets: [{
						label: "Mobile apps",
						tension: 0.4,
						borderWidth: 0,
						pointRadius: 0,
						borderColor: "#1890FF",
						borderWidth: 3,
						backgroundColor: gradientStroke1,
						fill: true,
						data: [50, 40, 300, 220, 500, 250, 400, 230, 500],
						maxBarThickness: 6

					},
					{
						label: "Websites",
						tension: 0.4,
						borderWidth: 0,
						pointRadius: 0,
						borderColor: "#141414",
						borderWidth: 3,
						backgroundColor: gradientStroke2,
						fill: true,
						data: [30, 90, 40, 140, 290, 290, 340, 230, 400],
						maxBarThickness: 6
					},
					],
				},
     			options: {
					layout: {
						padding: {
							top: 30,
							right: 15,
							left: 10,
							bottom: 5,
						},
					},
					responsive: true,
					maintainAspectRatio: false,
					plugins: {
						legend: {
							display: false,
						},
					},
					tooltips: {
						enabled: true,
						mode: "index",
						intersect: false,
					},
					scales: {
						y: {
							grid: {
								// display: true,
								// color: "rgba(0, 0, 0, .2)",
								// zeroLineColor: "#000000",
								// borderDash: [6],
								// borderDashOffset: [6],
								drawBorder: false,
								display: true,
								drawOnChartArea: true,
								drawTicks: false,
								borderDash: [5, 5]
							},
							ticks: {
								// suggestedMin: 0,
								// suggestedMax: 1000,
								// display: true,
								// color: "#8C8C8C",
								// font: {
								// 	size: 14,
								// 	lineHeight: 1.8,
								// 	weight: '600',
								// 	family: "Open Sans",
								// },
								display: true,
								padding: 10,
								color: '#b2b9bf',
								font: {
									size: 11,
									family: "Open Sans",
									style: 'normal',
									lineHeight: 2
								},
							},
						},
						x: {
							grid: {
								// display: false,
								drawBorder: false,
								display: true,
								drawOnChartArea: true,
								drawTicks: true,
								borderDash: [5, 5]
							},
							ticks: {
								// display: true,
								// color: "#8C8C8C",
								// font: {
								// 	size: 14,
								// 	lineHeight: 1.5,
								// 	weight: '600',
								// 	family: "Open Sans",
								// },
								display: true,
								color: '#b2b9bf',
								padding: 10,
								font: {
									size: 11,
									family: "Open Sans",
									style: 'normal',
									lineHeight: 2
								},
							},
						},
					},
				}
			});
		},
		// Right before the component is destroyed,
		// also destroy the chart.
		beforeDestroy: function () {
			this.chart.destroy() ;
		},
	})

</script>

<style lang="scss" scoped>
</style>