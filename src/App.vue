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
		<img src="./assets/todo-list.svg" alt="todo-list-svg" class="todo-img" />
		<!-- <p class="title">Vue Your TODOs</p> -->
		<p class="subtitle">Your TODOs powered by Vue</p>
	</div>
	<Todos />
</template>

<style scoped>
.heading {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 10px;
	width: 992px;
	height: 200px;
	margin: 20px auto;
}
.subtitle {
	padding: 0px 8px;
	width: 500px;
	color: #abd1c6;
	font-size: 52.11px;
	text-align: center;
	margin-top: 0;
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

.todo-img {
	width: 250px;
	height: auto;
}
</style>
