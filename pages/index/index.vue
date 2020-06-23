<template>
	<view>
		<view class="tip">getSreenShot 获取图片内容的回调</view>
		<screenShot @getSreenShot="getSreenShot">
			<div style="height: 100%; width: 100%; background-image: url('/static/banner.jpg'); background-repeat: no-repeat; background-size: 100% 100%;">
				
			</div>
		</screenShot>
	</view>
</template>

<script>
	import screenShot from '@/components/screen-shot/screen-shot.vue';
	export default {
		components: {
			screenShot
		},
		data() {
			return {
				windowWidth: '',
				windowHeight: ''
			};
		},
		onLoad() {
			let _this = this;
			uni.getSystemInfo({
				success: function(res) {
					_this.windowHeight = res.windowHeight + 100;
					_this.windowWidth = res.windowWidth;
				},
				fail: function(err) {
					console.log(err);
				}
			});
		},
		methods: {
			getSreenShot(r) {
				// 获取截图路径
				console.log('r', r);
			}
		}
	}
</script>

<style>
.tip{
	position: absolute;
	top: 0;
	left: 0;
	z-index:999
}
</style>
