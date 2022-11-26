<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue';
import NavVue from './components/Nav.vue';
import Todos from './components/Todos/Todos.vue';
</script>

<template>
	<NavVue />
	<div class="heading">
		<p class="title">Vue Your TODOs</p>
		<p class="subtitle">Lorem ipsum, dolor sit amet consectetur adipisicing elit.</p>
	</div>
	<Todos />
</template>

<style scoped>
.heading {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 0px;
	width: 992px;
	height: 200px;
	margin-inline: auto;
}
.subtitle {
	display: flex;
	flex-direction: column;
	align-items: flex-start;
	padding: 0px 8px;
	width: 500px;
	height: 35px;
	color: #abd1c6;
	font-size: 29.33px;
	text-align: center;
}
.title {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 0px;
	margin-bottom: 0;
	width: 981px;
	height: 112px;
	color: #fffffe;
	font-size: 92.59px;
}
</style>
