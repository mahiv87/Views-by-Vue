<script lang="ts">
import { ref } from 'vue';
export default {
	name: 'todo-input',
	setup() {
		const newTodo = ref('');
		const data = JSON.parse(`${localStorage.getItem('todos')}`) || '';
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
	<div class="input-container">
		<input type="text" id="todo-input" v-model="newTodo" />
		<p class="todo-button" @click="addTodo()">Submit</p>
	</div>
	<p>{{ newTodo }}</p>
</template>

<style scoped>
.input-container {
	display: flex;
	flex-direction: row;
	align-items: center;
	padding: 0px 60px;
	gap: 110px;

	width: 949px;
	height: 49px;
}

.todo-button {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	width: 119px;
	height: 47px;
	color: #001e1d;
	background: #f9bc60;
	border-radius: 30px;
	font-weight: 400;
	font-size: 22px;
	line-height: 27px;
}

.todo-button:hover {
	background: hsl(36, 93%, 72%);
	cursor: pointer;
	letter-spacing: 1px;
	transition: all ease-out 300ms;
}

#todo-input {
	width: 600px;
	height: 49px;
	padding-left: 10px;
	background: #fffffe;
	border-radius: 25px;
	border-color: #001e1d;
}
</style>
