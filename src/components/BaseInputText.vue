<template>
  <input
    type="text"
    class="input"
    :value="value"
    v-on="listeners"
  >
</template>

<script>
  export default {
    props: {
      value: {
        type: String,
        default: '',
      }
    },
    computed: {
      listeners () {
        return {
          ...this.$listeners,
          input: event => this.$emit('input', event.target.value)
        }
      }
    }
  }
</script>

<style>
  .input {
    width: calc(100% - 40px);
    display: border-box;
    padding: 20px;
    background: rgba(255,255,255,0.4);
    border: 3px;
    font-size: 20px;
    color: rgba(0,0,0,0.7);
    margin-bottom: 10px;
    font-weight: bold;
    font-size: 1.5rem;
    text-align: center;
  }

  ::placeholder {
    color: rgba(0,0,0,0.4);
  }
</style>
