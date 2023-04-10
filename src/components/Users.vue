<template>
  <h1>Candidats</h1>
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Nom</th>
        <th>Mail</th>
        <th>Ville</th>
      </tr>
    </thead>
    <tbody>
    <tr v-for="(un, index) in donnees" :key="index">
      <td>{{index+1}}</td>
      <td>{{un.name.first}} {{un.name.last}}</td>
      <td>{{un.email}}</td>
      <td>{{un.location.city}}</td>

    </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Users",
  data() {
    return {
      donnees: [],
    }
  },
  created() {
    this.axios
        .get('https://randomuser.me/api/?results=10').then(utilisateurs => {
      this.donnees = utilisateurs.data.results;
    })
  }
}
</script>

<style scoped>
th {
  background: lightgreen;
  font-size: 140%;
}

td {
  width: 10rem;
  text-align: center;
  border: teal 1px solid;
}

tr {

}
</style>