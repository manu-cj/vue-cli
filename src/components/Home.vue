<template>
  <h2>Welcome Stranger</h2>
  <h1>Liste des inscrits</h1>
  <inscrits :liste="personnes"></inscrits>
</template>

<script>
import Inscrits from "/src/components/Inscrits";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Home",
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


<style scoped>

</style>