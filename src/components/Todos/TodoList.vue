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
	<ul>
		<li v-for="todo in todos">
			<span>{{ todo.task }}</span>
		</li>
	</ul>
</template>

<style scoped></style>
