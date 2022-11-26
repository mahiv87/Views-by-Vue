<script lang="ts">
export default {
	data() {
		return {
			newTodo: ''
		};
	}
};
</script>

<template>
	<div class="input-container">
		<input type="text" id="todo-input" placeholder="Enter todo here..." v-model="newTodo" />
	</div>
	<p>{{ newTodo }}</p>
</template>

<style scoped></style>
