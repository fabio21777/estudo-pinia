<template>
	<div>
		<h1>Contador</h1>
		<h2>{{ count }}</h2>
		<h1>Contador * 2</h1>
		<h2> {{ doubleCount }} </h2>
		<el-button type="primary" @click="increment">+</el-button>
		<el-button type="danger" @click="decrement">-</el-button>
	</div>
</template>

<script setup lang="ts">
import { useCounterStore } from '../stores/counter'
import { storeToRefs } from 'pinia'
const store = useCounterStore()
const { count, doubleCount } = storeToRefs(store)
const { increment,decrement } = store
</script>
<style lang="">

</style>

