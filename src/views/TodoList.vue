<template>
	<div>
		<add-list @add-todo = "addList"/>
		<ul>
			<item-list
				v-for = "(todo, i) of todos"
				:key = "todo.id"
				:todo = "todo"
				:index = "i"
				v-on:remove-todo = "removeTodo"/>
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
			]}
		},

		methods:{
			addList(todo){
				this.todos.push(todo);
			},
			removeTodo(id){
				this.todos = this.todos.filter(t => t.id !== id)
			}
		},
		components:{
			AddList,ItemList 
		}
	}
</script>

<style scoped>
	ul{
		list-style: none;
		padding: 0;
		margin: 0;
	}
</style>