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
	},
	methods: {
		removeTodo(todo: string) {
			const index = this.todos.indexOf(todo);
			this.todos.splice(index, 1);
			localStorage.setItem('todos', JSON.stringify(this.todos));
		}
	}
};
</script>

<template>
	<ul class="list-container">
		<li v-for="todo in todos" class="todo-item">
			<span>{{ todo.task }} </span>
			<p class="remove-button" @click="removeTodo(todo)">X</p>
		</li>
	</ul>
</template>

<style scoped>
.list-container {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	padding: 0px;
	width: 100%;
}

.todo-item {
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 10px;
	width: 75%;
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
	cursor: pointer;
	padding: 5px 10px;
	background: #e16162;
	border-radius: 4px;
	font-size: 16.5px;
	font-weight: bold;
	line-height: 20px;
	color: #fffffe;
}

.remove-button:hover {
	background: #e14142;
}

@media screen and (max-width: 768px) {
	.todo-item {
		width: 100%;
	}
}
</style>
