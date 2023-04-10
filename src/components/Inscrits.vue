<template>
<table>
  <tr>
    <th>Prénom</th>
    <th>Nom</th>
    <th>Age</th>
  </tr>
  <tr v-for="personne in liste" :key="personne">
    <td>{{personne.prenom}}</td>
    <td>{{personne.nom}}</td>
    <td>{{personne.age}}</td>
  </tr>
</table>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Inscrits",
  props : ["liste"],

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
}
</style>