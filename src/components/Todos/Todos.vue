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
	<div class="todo-container">
		<TodoInput />
		<TodoList />
	</div>
</template>

<style scoped>
.todo-container {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 20px 14px;
	gap: 32px;
	max-width: 977px;
	/* height: 481px; */
	margin-top: 150px;
	margin-inline: auto;
	background: #e8e4e6;
	box-shadow: 7px 7px 10px 7px rgba(0, 0, 0, 0.25);
	border-radius: 5px;
}

@media screen and (max-width: 768px) {
	.todo-container {
		margin-top: 75px;
	}
}
</style>
