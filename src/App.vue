<template>
  <div id="app">
    <div v-if="showList">
      <example-list @item-selected="showForm" />
    </div>
    <div v-else>
      <example-form :item="selectedItem" @return-to-list="returnToList" />
    </div>
  </div>
</template>

<script>
import ExampleForm from "./components/exampleForm.vue";
import ExampleList from "./components/exampleList.vue";

export default {
  name: 'App',
  data() {
    return {
      showList: true,
      selectedItem: null,
    };
  },
  methods: {
    showForm(item) {
      this.selectedItem = item;
      this.showList = false;
    },
    returnToList() {
      this.showList = true;
    },
  },
  components: {
    ExampleForm,
    ExampleList
  },
};
</script>

<style>
body{
  background-color: #000 !important;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #fff;
  width: 520px !important;
  border-radius: 20px;
}
</style>
