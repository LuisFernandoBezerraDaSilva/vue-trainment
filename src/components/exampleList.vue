<template>
  <div class="field">
    <b-table-lite striped hover :items="items" @row-clicked="itemClicked" />
    <b-button type="submit" variant="primary" @click="showForm">teste</b-button>
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
        items: [
          { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
          { age: 38, first_name: 'Jami', last_name: 'Carney' }
        ]
      }
  },
  methods: {
    showForm() { 
      const selectedItem = this.items[0];
      this.$emit("show-form", selectedItem);
    },
    itemClicked(item) {
      // Emitir o evento "item-selected" com os dados do item selecionado
      this.$emit("item-selected", item);
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
