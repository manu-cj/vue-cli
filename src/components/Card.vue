<template>
  <div id="cards">
    <div class="card" v-for="(donnee, index) in donnees " :key="index">
      <div class="header-card">
        <h2>{{donnee.name.first}} {{donnee.name.last}}</h2>
      </div>
      <div class="main-card">
        <img :src="donnee.picture.large" alt="photo">
      </div>
      <div class="footer-card">
        <h3>{{donnee.location.city}}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Card",
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
#cards {
  width: 60%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-content: space-between;
  align-items: center;
}

.card {
  border: #ff6200 solid  2px;
  width: 18%;
  height: 300px;
  text-align: center;
  background-color: teal;
  border-radius: 5px;
  margin: 5px;
}

.header-card, .footer-card {
  height: 10%;
}

.main-card {
  height: 60%;
}

.main-card img {
  width: 100%;
  height: 90%;
}

</style>