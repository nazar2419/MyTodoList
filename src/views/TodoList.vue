<template>
	<div class="todos">
		<add-list  @add-todo = "addList"/>
		<ul>
			<item-list
				v-for = "(todo, i) of todos"
				:key = "todo.id"
				:todo = "todo"
				:changes ="changes"
				:index = "i"
				v-on:remove-todo = "removeTodo" />
		</ul>
	</div>
</template>

<script>
	import AddList from '@/components/AddList'
	import ItemList from '@/components/ItemList'
	export default {
		name:'todo',
		data(){
			return {
			todos:[
			{id:1, title: 'Купити молоко', completed:false},
			{id:2, title: 'Купити сир', completed:false},
			{id:3, title: 'Купити м\'ясо', completed:false}
			],
		}
		},
		methods:{
			addList(todo){
				this.todos.push(todo);
			},
			removeTodo(id){
				this.todos = this.todos.filter(t => t.id !== id)
			},
		},
		components:{
			AddList,ItemList 
		}
	}
</script>

<style scoped>
	*{
		padding:0;
	}
	ul{
		display: block;
		margin-left: auto;
		margin-right: auto;
		max-width:500px;
		border: 1
		
	}
</style>