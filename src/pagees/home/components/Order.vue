<template>
	<div class="order">
		<div class="spread">
			<a href="javascript:;" class="iconfont">&#xe606; 麻辣香锅坊旗舰店 &gt;</a>
			<span>点击领劵</span>
			<a href="javascript:;" @click="handleCoupon()">领劵</a>
		</div>
		<div class="order-list">
			<img src="http://s1.st.meishij.net/r/231/00/2937731/a2937731_146297683319666.jpg">
			<ul class="order-msg">
				<li>麻辣香锅龙虾套选组合装<span class="right">{{'￥' +money+ '.00'}}</span></li>
				<li>麻辣小龙虾 | 品牌店<span class="right">{{'x' + num}}</span></li><br>
				<li>5星 推荐指数5分<span class="mag">评论873条</span></li><br>
				<li>外卖￥30元起送 | 免费配送 <span class="mag" color="ash">30分钟</span></li><br>
			</ul>
		</div>
		<div class="order-num">
			<div class="list-sum">
				<span class="order-sum">数量</span>
				<ul class="iconfont order-count">
					<li @click="plus()">&#xe605;</li>
					<li>{{num}}</li>
					<li @click="pop()">&#xe604;</li>
				</ul>
			</div>
			<div class="activity">
				<div class="le">抵用券</div>
				<div class="ri">满100减50</div>
			</div>
			<div class="express">
				<div class="le">快递运费</div>
				<div class="ri">快递免邮</div>
			</div>
		</div>
	</div>
</template>

<script>
export default{
	name : 'SectionOrder',
	data () {
		return {
			num : 1,
			money : 60,
			couponSum : null,
			couponAfter : null
		}
	},
	methods : {
		handleCoupon (){
			var randomSum = Math.random()	//0.0....~0.1....
			var toFed = randomSum.toFixed(1)	//保留一位小数
			this.couponSum = toFed	//更新折扣
			this.num = 1	//初始化
			if(this.money == 0){	//当打折的价格等于0后,免单生成
				confirm('恭喜获得免单！！！')
				return
			}else{
				confirm(toFed + '折')
			}
		},
		plus (){
			this.num++
			if(this.couponAfter !== null){	//如果用户不点击领劵时
				this.money += parseInt(this.couponAfter)	//增加或减小数量也需要转换
			}else{
				this.money += 60
			}
			
		},
		pop (){
			if(this.num < 2) return	//防止用户数量小于1数量时
			this.num--
			if(this.couponAfter !== null){
				this.money -= parseInt(this.couponAfter)
			}else{
				this.money -= 60
			}
		}
	},
	watch : {	//监听随机折扣的数据
		couponSum (val){	//val(this.couponSum)
			this.couponAfter = this.money * this.couponSum	//折扣后 = 原价 * 折扣
			this.money = parseInt(this.couponAfter)		//60 * 折扣会有小数出现，更新数据
		}
	}
}
</script>

<style lang="stylus" scoped>
	.order	//订单列表
		margin-top:.2rem
		background-color:#e5e3e3
		.spread
			width:100%
			height:.6rem
			line-height:.6rem
			border-bottom:1px solid #e5e3e3
			background-color:white
			font-size:.2rem
			a
				font-size:.2rem
				color:black
			a:nth-of-type(1)
				float:left
				margin-left:.1rem
			a:nth-of-type(2)
				width:.75rem
				height:.4rem
				line-height:.45rem
				float:right
				margin-right:.3rem
				border-radius:.18rem
				background-color:red
				text-align:center
				color:white
				margin-top:.1rem
		.order-list
			display:flex
			height:1.7rem
			padding:.2rem
			flex-wrap:wrap
			margin-bottom:.2rem
			background-color:white
			img
				width:1.7rem
				height:1.65rem
				border-radius:.1rem
			.order-msg
				flex:1
				font-size:.1rem
				margin-left:.2rem
			li
				.right
					float:right
					font-size:.1em !important
					color:#888
			li:nth-of-type(1)
				font-size:.25rem
				font-weight:bold
				margin-bottom:.1rem
			li:nth-of-type(2)
				color:#888
			li:nth-of-type(3)
				color:#888
			li:nth-of-type(4)
				color:red
			.mag
				margin-left:1.4rem
			[color=ash]
				margin-left:.25rem !important
				color:black
		.list-sum,.activity,.express
			background-color:white
		.order-num
			width:100%
			background-color:#e5e3e3
			.list-sum
				display:flex
				padding:.255rem
				border-bottom:1px solid #e5e3e3
				.order-sum
					float:left
				.order-count
					flex:1
					li
						margin-left:.2rem
						float:right
		.activity,.express
			display:flex
			padding:.255rem
			background-color:white
			.le
				float:left
			.ri
				flex:1
				text-align:right
				color:red
				font-size:1.2em
				font-weight:bold
		.activity
			margin-bottom:.2rem
</style>