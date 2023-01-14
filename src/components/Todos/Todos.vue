<script lang="ts">
import TodoInput from './TodoInput.vue';
import TodoList from './TodoList.vue';

export default {
	name: 'Todos',
	components: {
		TodoInput,
		TodoList
	}
};
</script>

<template>
	<section class="todo-container">
		<TodoInput />
		<TodoList />
	</section>
</template>

<style scoped>
.todo-container {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 20px 14px;
	max-width: 768px;
	margin-block: 150px 75px;
	margin-inline: auto;
	background: #e8e4e6;
	box-shadow: 7px 7px 10px 7px rgba(0, 0, 0, 0.25);
	border-radius: 5px;
}

.todo-container::before {
	display: block;
	position: absolute;
	top: -290px;
	content: '';
	width: 200px;
	height: 600px;
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(0, 124, 121, 1) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(40px);
	transform: rotate(-60deg);
	z-index: -1;
}

.todo-container::after {
	display: block;
	position: absolute;
	top: -260px;
	content: '';
	width: 200px;
	height: 600px;
	border-radius: 50%;
	background: radial-gradient(
		circle,
		rgba(249, 188, 96, 0.3) 0%,
		rgba(0, 70, 67, 1) 100%
	);
	filter: blur(40px);
	transform: rotate(60deg);
	z-index: -2;
}

@media screen and (max-width: 992px) {
	.todo-container {
		margin-block: 50px;
		margin-inline: 10px;
	}

	.todo-container::before {
		display: block;
		position: absolute;
		top: -100px;
		content: '';
		width: 100px;
		height: 300px;
		border-radius: 50%;
		background: radial-gradient(
			circle,
			rgba(0, 124, 121, 1) 0%,
			rgba(0, 70, 67, 1) 100%
		);
		filter: blur(20px);
		transform: rotate(-60deg);
		z-index: -1;
	}

	.todo-container::after {
		display: block;
		position: absolute;
		top: -80px;
		content: '';
		width: 100px;
		height: 300px;
		border-radius: 50%;
		background: radial-gradient(
			circle,
			rgba(249, 188, 96, 0.3) 0%,
			rgba(0, 70, 67, 1) 100%
		);
		filter: blur(20px);
		transform: rotate(60deg);
		z-index: -2;
	}
}
</style>
