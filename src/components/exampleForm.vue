<template>
  <div>
    <b-form @submit="enviarFormulario">
      <b-form-group label="Nome:" label-for="nome">
        <b-form-input id="nome" v-model="nome"></b-form-input>
      </b-form-group>

      <b-form-group label="Idade:" label-for="idade">
        <b-form-input id="idade" v-model="idade" type="number"></b-form-input>
      </b-form-group>

      <b-form-group label="Email:" label-for="email">
        <b-form-input id="email" v-model="email" type="email"></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Enviar</b-button>
    </b-form>
    <b-button @click="test">Enviar</b-button>
  </div>
</template>


<script>
import { BForm, BFormGroup, BFormInput, BButton } from 'bootstrap-vue'

export default {
  name: 'exampleList',
  props: {
    msg: String,
    item: Object, 
  },
  data() {
    return {
      nome: '',
      idade: null,
      email: ''
    };
  },
  components: {
    BForm,
    BFormGroup,
    BFormInput,
    BButton
  },
  methods: {
    test() {
      console.log(JSON.parse(JSON.stringify(this.item)))
    },
    enviarFormulario() {
      var urlApi = 'http://localhost:3003'
      console.log('Nome:', this.nome);
      console.log('Idade:', this.idade);
      console.log('Email:', this.email);

      const url = urlApi + '/postForm';
      const data = {
        campo1: this.campo1,
        campo2: this.campo2,
      };

      fetch(url, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json', 
        },
        body: JSON.stringify(data), 
      })
        .then(response => {
          if (!response.ok) {
            throw new Error('Erro na requisição: ' + response.status);
          }
          return response.json();
        })
        .then(responseData => {
          console.log('Resposta da API:', responseData);
        })
        .catch(error => {
          console.error('Ocorreu um erro na requisição:', error);
        });

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
