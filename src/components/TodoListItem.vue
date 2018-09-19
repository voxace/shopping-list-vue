<template>
  <li @click="$emit('remove', todo.id)">
    {{ todo.text }}
  </li >
</template>

<script>
  export default {
    props: {
      todo: {
        type: Object,
        required: true
      }
    }
  }
</script>

<style>
  li{
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
    font-family: arial;
    font-size: 20px;
    cursor: pointer;
    letter-spacing: 1px;
    background: rgba(255,255,255,0.05);
    margin: 5px 0px;
  }

  li:hover{
    text-decoration: line-through;
    background: rgba(255,255,255,0.1);
  }
</style>
