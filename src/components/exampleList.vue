<template>
  <div class="field">
    <div class="mt-2">Nome: {{ text }}</div>
    <b-form-input v-model="text" placeholder="Enter your name"></b-form-input>
    <div class="mt-2">Idade: {{ text }}</div>
    <b-form-input v-model="text" placeholder="Enter your name"></b-form-input>
    <div class="mt-2">Email: {{ text }}</div>
    <b-form-input v-model="text" placeholder="Enter your name"></b-form-input>
    <b-button variant="success">Send</b-button>
    
  </div>
</template>

<script>
export default {
  name: 'exampleList',
  props: {
    msg: String
  },
  data() {
      return {
        types: [
          'text',
        ]
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

button {
  margin-top: 16px;
}
.field{
  margin: 16px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
