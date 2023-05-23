<script>
import HeaderApp from "./components/HeaderApp.vue";
import CardList from "./components/CardList.vue";
import axios from "axios";
import { store } from "./store.js";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    HeaderApp,
    CardList,
  },

  created() {
    // qui fare la richiesta all'api
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0%27")
      .then((response) => (this.store.cardList = response.data.data));

    axios
      .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((response) => (this.store.arrselect = response.data));
  },
};
</script>

<template>
  <HeaderApp />
  <input type="text" />
  <main>
    <CardList />
  </main>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.html {
  font-family: "Montserrat", sans-serif;
}

.container {
  margin: 0 auto;
  padding: 1rem;
  max-width: 1000px;
}

h1 {
  text-align: center;
}
select {
  margin: 1rem;
}
</style>
