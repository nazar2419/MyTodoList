<template>
	<li >
		<span :class = "{ check: todo.completed }">
			<input type = "checkbox"
			v-on:change = "todo.completed = !todo.completed">	
			<strong>{{index + 1}}</strong>
			{{todo.title | upperCase()}}
		</span>
		<div>
		<button @click="$emit('remove-todo', todo.id)">Remove</button>
		</div>
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
		display: flex;
		justify-content: space-between;
		padding: .5rem 1rem;
		margin-bottom: 1rem;
		background:rgba(255,255,0,0.1);
	}
	input {
		margin-right: 1rem;	
	}

	.check{
		text-decoration:line-through;	
	}
	button{
		margin: 0 5px;
	}

</style>