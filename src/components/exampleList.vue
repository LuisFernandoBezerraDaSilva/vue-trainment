<template>
  <div class="field">
    <b-table-lite striped hover :items="items"></b-table-lite>
    
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
