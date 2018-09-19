<template>
	<div id="app">
		<h1>Shopping List</h1>
		<TodoList/>
	</div>
</template>

<script>
  import TodoList from './components/TodoList.vue'

  export default {
  	components: {
  		TodoList
  	}
  }
</script>

<style>
  body{
    background: #0d1521;
    font-family: tahoma;
    color: #989898;
    text-align: center;
  }
</style>
