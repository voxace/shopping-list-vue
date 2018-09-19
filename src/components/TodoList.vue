<template>
	<div id="container">
		<BaseInputText
			v-model="newTodoText"
			placeholder="New item"
			@keydown.enter="addTodo"
		/>
		<ul v-if="todos.length">
			<TodoListItem
				v-for="todo in todos"
				:key="todo.id"
				:todo="todo"
				@remove="removeTodo"
			/>
		</ul>
		<p v-else>
			Nothing left in the list. Add a new todo in the input above.
		</p>
	</div>
</template>

<script>
  import BaseInputText from './BaseInputText.vue'
  import TodoListItem from './TodoListItem.vue'

  let nextItemID = 1

  export default {
  	components: {
  		BaseInputText, TodoListItem
  	},
    data () {
      return {
  			newTodoText: '',
        todos: [
  				{
  					id: nextItemID++,
  					text: 'Eggs'
  				},
  				{
  					id: nextItemID++,
  					text: 'Milk'
  				},
  				{
  					id: nextItemID++,
  					text: 'Bread'
  				}
  			]
      }
    },
  	methods: {
  		addTodo () {
  			const trimmedText = this.newTodoText.trim()
  			if (trimmedText) {
  				this.todos.push({
  					id: nextItemID++,
  					text: trimmedText
  				})
  				this.newTodoText = ''
  			}
  		},
  		removeTodo (idToRemove) {
  			this.todos = this.todos.filter(todo => {
  				return todo.id !== idToRemove
  			})
  		}
  	}
  }
</script>

<style>
  #container {
    position: relative;
    width: 95%;
    background: #090d13;
    margin: 0 auto;
    padding: 20px;
    box-sizing: border-box;
  }

  ul{
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
</style>
