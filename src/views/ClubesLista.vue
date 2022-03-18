<template>
  <v-container>
    <h2 class="text-h5 text-center mt-3 mb-5">Classificação</h2>

    <ClubesTabela :clubes="clubesOrdenados"/>
    
  </v-container>
</template>

<script>
import ClubesTabela from '../components/ClubesTabela.vue'

export default {
  name: "ClubesLista",
  components: {
      ClubesTabela
  },
  data() {
    return {
      clubesLista: [],
    };
  },
  created() {
    fetch("https://hackthon-decola.firebaseio.com/clubes-lista.json")
      .then((response) => response.json())
      .then((json) => {
        this.clubesLista = json;
      });
  },
  computed: {
      clubesOrdenados() {
          const listaComputada = this.clubesLista.slice(0).sort(
              (a,b) => a.pontos > b.pontos ? -1 : 1
          )
          return listaComputada;
      }
  }
};
</script>

<style scoped>
</style>