<template>
	<view class="content">
		<reserve-date @change='change' :startDate='startDate' :price='price' :isNowDate='isNowDate' :disableBefore='disableBefore' :endDate='endDate'/>
	</view>
</template>

<script>
	import reserveDate from '@/components/reserve-date/reserve-date.vue'
	export default {
		data() {
			return {
				price: {
					type: true,
					data: []
				},
				isNowDate: true,
				disableBefore: true,
				endDate: '2019-5-26',
				startDate: '2019-5-15'
			}
		},
		mounted() {
			for (var i = 0; i < 31; i++) {
				let price = parseInt(Math.random() * 1000)
				this.price.data.push(price)
			}
		},
		methods: {
			change(date) {
				console.log(date)
			}
		},
		components: {
			reserveDate
		}
	}
</script>


<style lang="scss" scoped>

</style>
