<template>
  <Road></Road>
</template>

<script>

import Road from "@/components/Road";

export default {
  name: "App",
  components: {

    Road,
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