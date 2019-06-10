<template>
	<div class="hander">
		<div class="data">
			<ul class="iconfont icon-flex">
				<li>
					<i v-for="itemI of oI" :key="itemI.id" class="iColor"></i>
					千图网
					&#xe75c;
				</li>
				<li v-html="handleDate()"></li>
				<li>
					&#xe607;72%&#xe652;
				</li>
			</ul>
		</div>
		<div class="confirm">
			<ul class="iconfont confirm-flex">
				<li></li>
				<li>确认订单</li>
				<li>&#xe624;</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default{
	name: 'IndexHander',
	data (){
		return {
			oI : [{id:'01'},{id:'02'},{id:'03'},{id:'04'},{id:'05'}]
		}
	},
	methods : {
		handleDate (){
			var date = new Date(),
				hours = date.getHours(),
				minutes = date.getMinutes()
			function initDate(objD){	//是否到达10，没到达加0
				return objD < 10 ? '0' + objD : '' + objD
			}
			return hours + ' : ' + initDate(minutes)
		}
	}
}
</script>

 <style lang="stylus" scoped>
 	.hander
 		width:100%
 		height:1rem
 		background-color:deepskyblue
 		.data	/* 手机头部消息与时间*/
 			width:100%
 			height:.4rem
 			line-height:.1rem
 			background-color:orange
 			.icon-flex
 				display:flex
 				width:100%
 				li
 					margin:.15rem .1rem
 				li:nth-of-type(1)
 					float:left
 					font-size:.2rem
 					.iColor
 						display:block
 						width:.1rem
 						height:.1rem
 						background-color:black
 						border-radius:50%
 						float:left
 						margin-right:.04rem
 					i.iColor:nth-of-type(4)
 						background-color:white
 					i.iColor:nth-of-type(5)
 						background-color:white
 				li:nth-of-type(2)
 					flex:1
 					font-size:.8em
 					text-align:center
 				li:nth-of-type(3)
 					float:right
 					font-size:.8em
 					margin-left:.6rem
 		.confirm /*确认订单*/
 			width:100%
 			height:.6rem
 			background-color:aqua
	 		.confirm-flex
	 			display:flex
	 			width:100%
	 			padding:.1125rem 0
	 			li:nth-of-type(1)
	 				float:left
	 				width:0
	 				height:0
	 				border-top:.5em solid transparent
	 				border-left:.5em solid transparent
	 				border-bottom:.5em solid transparent
	 				border-right:.5em solid black
	 				margin-left:.05rem
	 				margin-right:.35rem
	 			li:nth-of-type(2)
	 				flex:1
	 				text-align:center
	 				font-weight:bolder
	 			li:nth-of-type(3)
	 				float:right
	 				margin-right:.2rem
 </style>