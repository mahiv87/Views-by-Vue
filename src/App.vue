<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import NavVue from './components/Nav.vue';
import Todos from './components/Todos/Todos.vue';
import Footer from './components/Footer.vue';
</script>

<template>
	<NavVue />
	<header class="heading">
		<img src="./assets/todo-list.svg" alt="todo-list-svg" class="todo-img" />
		<p class="subtitle">Your TODOs powered by Vue</p>
	</header>
	<Todos />
	<Footer />
</template>

<style scoped>
.heading {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 10px;
	max-width: 992px;
	height: 200px;
	margin: 50px auto;
}
.subtitle {
	/* position: relative;
	top: -1270px; */
	padding: 0px 8px;
	max-width: 500px;
	color: #abd1c6;
	font-size: 39.09px;
	font-style: italic;
	text-align: center;
	margin: 25px 0px;
}
.title {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 0px;
	margin-bottom: 0;
	max-width: 981px;
	/* height: 112px; */
	color: #fffffe;
	font-size: 92.59px;
}

.todo-img {
	width: 250px;
	height: auto;
	margin-top: 25px;
}

/* p::after {
	display: block;
	content: '';
	position: relative;
	top: -10%;
	left: 0%;
	width: 600px;
	height: calc(100vh - 10rem);
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(0, 124, 121, 1) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(50px);
	transform: rotate(-60deg);
	z-index: -2;
} */

/* .subtitle::after {
	display: block;
	content: '';
	position: relative;
	top: -20%;
	left: 0%;
	width: 600px;
	height: calc(100vh - 10rem);
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(249, 188, 96, 0.3) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(50px);
	transform: rotate(60deg);
	z-index: -1;
} */

@media screen and (max-width: 992px) {
	.subtitle {
		top: 0;
		font-size: 22px;
		margin-bottom: 75px;
	}

	p::after {
		display: none;
	}

	.subtitle::after {
		display: none;
	}
}
</style>
