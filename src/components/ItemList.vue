<template>
	<li>
		<span :class = "{ check: todo.completed }">
			<input type = "checkbox"
			v-on:change = "todo.completed = !todo.completed">	
			<strong>{{index + 1}}</strong>
			{{todo.title | upperCase()}}
		</span> 
		<button @click="$emit('remove-todo', todo.id)">Delete</button>
	</li>
</template>
<script>
	export default{
		props:{
			todo:{
				type: Object,
				required: false
			},
			index:Number
		},
		filters: {
			upperCase(value) {
				return value.toUpperCase()
			}
		}
	}
</script>

<style scoped>
	li {
		border: 1px solid #ccc;
		display: flex;
		justify-content: space-between;
		padding: .5rem 1rem;
		margin-bottom: 1rem;
	}
	input {
		margin-right: 1rem;
	}
	.check{
		text-decoration:line-through;
	}
</style>