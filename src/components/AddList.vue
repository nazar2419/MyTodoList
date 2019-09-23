<template>
	<form @submit.prevent = "onSubmit"  class = "form">
		<input type = "text"  maxlength="26" v-model = "title"  class = "title">
		<button class = "submit">Add</button>
	</form>
</template>

<script>
import TodoList from '@/views/TodoList'
	export default {
		data(){
			return {
				title:''
			}
		},
		methods:{
			onSubmit(){
				if (this.title.trim()) {
					const newTodo = {
					id:Math.floor( Math.random() * 10000000 ),
					title:this.title,
					completed:false
					}
				this.$emit('add-todo', newTodo)
				this.title = ''
				}
			}

		},
		comonents:{
			TodoList
		}
	}
</script>
<style scoped>
	form {
		text-align: center;
	}
	input {
		flex-grow: 1;
		width: 300px;
		margin-bottom: 10px;
		height: 28px;
		font-size: 18px;
		text-indent: 10px;
		position: relative;
	}
	.submit{
		box-sizing: content-box;
		height: 28px;
        font-size: 18px;
	
	}
	
	
</style>