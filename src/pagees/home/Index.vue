<template>
	<div>
		<index-hander></index-hander>
		<section-order></section-order>
	</div>
</template>
<script>
import IndexHander from './components/Hander.vue'
import SectionOrder from './components/Order.vue'
export default{
	name : 'Index',
	components: {
		IndexHander,
		SectionOrder
	}
}
</script>
<style></style>