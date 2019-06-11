<template>
	<div class="payment">
		<p class="title-payment">选择支付方式</p>
		<ul>
			<li v-for="(cardItem,index) of cardList" :key="cardItem.id" class="card-list">
				<img :src="cardItem.url" class="img-card">
				<div class="fee-list">
					<span>{{cardItem.cardTitle}}</span>
					<br>
					<i></i>
					<span>
						{{cardItem.fee}}
						<strong>{{cardItem.money}}</strong>
					</span>
				</div>
				<div class="iconfont hook">
					<a href="javascript:;" 
					   class="icon-style"
					   :class="{'icon-dagou':index == toggle}" 
					   @click="toggle = index;handleHook(index)">
					   <!-- 添加图标类根据index下标开始，每次点击toggle都同步index -->
					   </a>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default{
	name : 'SectionPayment',
	data () {
		return {
			cardList : [{
				id : '01',
				url : 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1560273118774&di=c31c2155098d63490c52392ad5417b9b&imgtype=0&src=http%3A%2F%2Fbpic.588ku.com%2Felement_origin_min_pic%2F17%2F02%2F12%2F0f4c591cf572d0646c1c970f47e9b766.jpg',
				cardTitle : '千库银行储蓄卡(为好0987)',
				fee : '单笔可消费',
				money : '8000'
			},
			{
				id : '02',
				url : 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=4032572166,2033709585&fm=26&gp=0.jpg',
				cardTitle : '千库银行储蓄卡(为好9982)',
				fee : '单笔可消费',
				money : '9000'
			},
			{
				id : '03',
				url : 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1560273304043&di=0d1a36055f39838da5438f6cb4070ff3&imgtype=0&src=http%3A%2F%2Fimg.bqatj.com%2Fimg%2Fdcc144fbe0414131.jpg',
				cardTitle : '移动支付快捷支付',
				fee : '账号 182****0013'
			},
			{
				id : '04',
				url : 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1560273367403&di=43f128ec02c6a760f44e9cf93f0269e9&imgtype=0&src=http%3A%2F%2Fm1.biz.itc.cn%2Fpic%2Fnew%2Fn%2F88%2F77%2FImg5817788_n.jpg',
				cardTitle : '移动支付快捷支付',
				fee : '账号 176****8865'
			}],
			toggle : 0,
			active : false
		}
	},
	methods : {
		handleHook (index){
			console.log(index);
		}
	}
}
</script>

<style lang="stylus" scoped>
	.payment
		width:100%	
		.title-payment
			margin:.2rem
		ul
			li.card-list
				display:flex
				box-sizing:border-box
				padding:.2rem .2rem
				height: 1.1rem
				border-bottom:1px solid #e5e3e3
				background-color:white
				.img-card
					width:.8rem
					height:.7rem
				.fee-list
					margin-left:.3rem
					strong
						color:red !important
					i
						display:block
						height:.15rem
					span:nth-last-child(1)
						color:#999
				.hook
					flex:1
					a
						display:block
						float:right
						width:.5rem
						height:.5rem
						border-radius:50%
						background-color:#e6e6e6
						margin-top:.1rem
					.icon-style
						font-size:.5rem
						color:red
					a.on
						background-color:red
</style>