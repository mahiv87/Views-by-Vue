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
			<span>{{ todo.task }} </span>
			<p class="remove-button">Remove</p>
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
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	padding: 10px;
	width: 830px;
	height: 30px;
	font-weight: 400;
	font-size: 16.5px;
	line-height: 20px;
	color: #fffffe;
	background: #004643;
	border-radius: 5px;
	margin-block: 5px;
}

.remove-button {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 5px 10px;
	gap: 10px;
	width: 77px;
	height: 30px;
	background: #e16162;
	border-radius: 30px;
	font-size: 16.5px;
	line-height: 20px;
	color: #fffffe;
}
</style>
