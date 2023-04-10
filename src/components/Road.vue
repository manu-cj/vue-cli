
<script>
import Home from "@/components/Home";
import Users from './Users.vue';
import Card from "@/components/Card";
import NotFound from './NotFound.vue';

const routes = {
  '?c' : Home,
  '?c=home': Home,
  '?c=users': Users,
  '?c=cards' : Card,
}

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name : "Road",
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '?c'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash
    })
  }
}
</script>

<template>
  <a href="#?c=home">Home</a> |
  <a href="#?c=users">Users</a> |
  <a href="#?c=cards">Cards</a> |
  <a href="#?c=non-existent-path">Broken Link</a>
  <component :is="currentView" />
</template>