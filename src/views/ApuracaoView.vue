<template>
  <div class="apuracao">
    <table>
      <tr>
        <th>Candidato</th>
        <th>Qtde votos</th>
        <th>Percentual</th>
      </tr>
      <tr v-for="candidato in candidatos" :key="candidato.nm">
        <td>{{candidato.nm}}</td>
        <td>{{candidato.vap}}</td>
        <td>{{candidato.pvap}}%</td>
      </tr>
    </table>
  </div>
</template>

<script>

export default {
  name: "ApuracaoView",
  data() {
    return {
      candidatos: {}

    }
  },
  methods: {
    async getApuracao() {
      const req = await fetch("https://resultados.tse.jus.br/oficial/ele2022/544/dados-simplificados/br/br-c0001-e000544-r.json")
      const data = await req.json()
      console.log(data.cand)
      this.candidatos = data.cand
    }
  },
  mounted() {
    this.getApuracao()
  }
}
</script>

<style scoped>
  table {
    margin: 20px auto;
  }

  td, th {
    padding: .7em;
    border: 1px solid grey;
  }
</style>

