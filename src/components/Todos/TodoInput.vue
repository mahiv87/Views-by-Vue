<script lang="ts">
import { ref } from 'vue';
export default {
	name: 'todo-input',
	data() {
		return {
			todos: JSON.parse(`${localStorage.getItem('todos')}`) || []
		};
	},
	setup() {
		const newTodo = ref('');
		const initialData: { task: string }[] = [
			{
				task: 'Finish Views project'
			}
		];
		const data = JSON.parse(`${localStorage.getItem('todos')}`) || initialData;
		const todos = ref(data);

		function addTodo() {
			if (newTodo.value) {
				todos.value.push({
					task: newTodo.value
				});
				newTodo.value = '';
			}
			saveData();
		}

		function saveData() {
			const storageData = JSON.stringify(todos.value);
			localStorage.setItem('todos', storageData);
		}

		function removeTodo(i: number) {
			todos.value.splice(i, 1);
			saveData();
		}

		return {
			todos,
			newTodo,
			addTodo,
			saveData,
			removeTodo
		};
	}
};
</script>

<template>
	<form class="input-container" @submit="addTodo()">
		<input type="text" id="todo-input" v-model="newTodo" />
		<button class="todo-button" type="submit">Submit</button>
	</form>
</template>

<style scoped>
.input-container {
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	max-width: 768px;
}

.todo-button {
	background: #f9bc60;
	color: #001e1d;
	margin: 10px;
	padding: 10px;
	border: none;
	border-radius: 4px;
	font-weight: bold;
}

.todo-button:hover {
	background: #f9ac50;
	cursor: pointer;
	transition: all ease-out 300ms;
}

#todo-input {
	width: 600px;
	height: 35px;
	background: #fffffe;
	border: none;
	border-radius: 4px;
}

@media screen and (max-width: 768px) {
	.input-container {
		width: 100%;
		display: flex;
		flex-direction: column;
	}

	#todo-input {
		width: 100%;
	}
}
</style>
