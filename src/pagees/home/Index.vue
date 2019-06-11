<template>
	<div>
		<index-hander></index-hander>
		<section-order></section-order>
		<section-payment></section-payment>
		<section-footer></section-footer>
	</div>
</template>
<script>
import IndexHander from './components/Hander.vue'
import SectionOrder from './components/Order.vue'
import SectionPayment from './components/Payment.vue'
import SectionFooter from './components/Footer.vue'
export default{
	name : 'Index',
	components: {
		IndexHander,
		SectionOrder,
		SectionPayment,
		SectionFooter
	}
}
</script>
<style></style>