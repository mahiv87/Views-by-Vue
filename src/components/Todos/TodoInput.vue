<script lang="ts">
import { ref } from 'vue';
export default {
	name: 'todo-input',
	setup() {
		const newTodo = ref('');
		const initialData = [
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
	<div class="input-container">
		<input type="text" id="todo-input" v-model="newTodo" />
		<p class="todo-button" @click="addTodo()">Submit</p>
	</div>
</template>

<style scoped>
.input-container {
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	max-width: 949px;
	/* padding: 0px 60px; */
	/* height: 49px; */
}

.todo-button {
	background: #f9bc60;
	color: #001e1d;
	margin-inline: 10px;
	padding: 10px;
	border-radius: 4px;
	font-weight: bold;
	/* display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	max-width: 119px;
	height: 47px;
	color: #001e1d;
	background: #f9bc60;
	border-radius: 30px;
	font-weight: 400;
	font-size: 22px;
	line-height: 27px; */
}

.todo-button:hover {
	background: hsl(36, 93%, 72%);
	cursor: pointer;
	transition: all ease-out 300ms;
}

#todo-input {
	width: 600px;
	height: 35px;
	/* max-width: 600px;
	height: 49px;
	padding-left: 10px;
	background: #fffffe;
	border-radius: 25px;
	border-color: #001e1d; */
}

@media screen and (max-width: 992px) {
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
