<script setup lang="ts">
import TodoInput from './TodoInput.vue';
</script>

<template>
	<div class="todo-container">
		<TodoInput />
	</div>
</template>

<style scoped>
.todo-container {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 20px 14px;
	gap: 32px;
	width: 977px;
	height: 481px;
	margin-top: 150px;
	margin-inline: auto;
	background: #e8e4e6;
	box-shadow: 7px 7px 10px 7px rgba(0, 0, 0, 0.25);
	border-radius: 5px;
}
</style>
