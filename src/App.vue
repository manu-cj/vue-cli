<template>
  <h1>Liste des inscrits</h1>
  <inscrits :liste="personnes"></inscrits>
</template>

<script>
import Inscrits from "./components/Inscrits.vue";

export default {
  name: "App",
  components: {
    Inscrits,
  },
  data() {
    return {
      personnes: [
        {prenom: "Jean", nom: "Bréhat", age: 20},
        {prenom: "Léa", nom: "Prijean", age: 25},
        {prenom: "Chris", nom: "Martin", age: 38},
        {prenom: "Pierre", nom: "Petit", age: 18},
      ]
    }

  }
}
</script>

<style>

</style>