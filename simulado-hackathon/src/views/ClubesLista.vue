<template>
  <v-simple-table>
    <template>
      <thead>
        <tr>
          <th class="text-left"> Classificação </th>
          <th class="text-left"> Time </th>
          <th class="text-center"> Pontos </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(time, index) in clubesListaOrdenada" :key="time.id">
          <td>
                <v-list-item-icon v-if= "index == 0">
                      <v-icon>mdi-crown</v-icon>
                </v-list-item-icon>
              {{ index + 1 }}</td>
          <td class="text-left">{{ time.nome }}</td>
          <td class="text-center">{{ time.pontos }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
export default {
    name: 'ClubesLista',
    data() {
        return {
            lista: []
        }
    },
    computed: {
        clubesListaOrdenada() {
            const listaOrdenada = this.lista.slice(0).sort(
                (a, b) => a.pontos > b.pontos ? -1 : 1
            )
            return listaOrdenada
        }
    },
    created() {
        fetch('https://hackthon-decola.firebaseio.com/clubes-lista.json')
            .then(response => response.json())
            .then(json => {
                this.lista = json
            })
    }
}
</script>

<style scoped>

</style>