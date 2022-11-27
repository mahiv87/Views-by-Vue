<script lang="ts">
import { ref } from 'vue';
export default {
	name: 'todo-list',
	setup() {
		const initialData: { task: string }[] = [
			{
				task: 'Finish Views project'
			}
		];
		const data = JSON.parse(`${localStorage.getItem('todos')}`) || initialData;
		const todos = ref(data);

		return {
			todos
		};
	}
};
</script>

<template>
	<ul class="list-container">
		<li v-for="todo in todos" class="todo-item">
			<span>{{ todo.task }}</span>
		</li>
	</ul>
</template>

<style scoped>
.list-container {
	display: flex;
	flex-direction: column;
	justify-content: start;
	align-items: center;
	padding: 0px;
	width: 900px;
	height: 360px;
}

.todo-item {
	list-style: none;
	padding: 5px 25px;
	gap: 10px;
	width: 900px;
	height: 40px;
}
</style>
