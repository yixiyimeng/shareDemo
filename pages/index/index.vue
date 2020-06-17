<template>
	<view>
		<view class="tip">getSreenShot 获取图片内容的回调</view>
		<screenShot @getSreenShot="getSreenShot">
			<image src="/static/banner.jpg" mode="" :style="{
                        height: windowHeight + 'px',
                        width: windowWidth + 'px'
                    }"></image>
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
					_this.windowHeight = res.windowHeight;
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
