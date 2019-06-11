<template>
	<div class="footer">
		<div>共计2件,合计<span>￥120.0</span></div>
		<button>提交订单</button>
	</div>
</template>

<script>
export default{
	name : 'SectionFooter'
}
</script>

<style lang="stylus" scoped>
	.footer
		user-select:none
		box-sizing:border-box
		height:1.5rem
		background-color:rgba(0,0,0,.8)
		padding: .4rem .2rem
		*
			display:inline-block
			color:white
			font-size:.1rem
		div
			vertical-align:-0.33rem
		button
			float:right
			width:2.7rem
			height:.7rem
			border-radius:.6rem
			background-color:red
		button:active
			background-color:#f56565
		span
			color:red
			font-size:.35rem
</style>