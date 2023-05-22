<script>
import CardApp from "./CardApp.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    CardApp,
  },
};
</script>

<template>
  <select name="" id="" placeholder="Seleziona">
    <option value="">Seleziona qui</option>
  </select>

  <div class="cards-container">
    <CardApp
      v-for="(card, index) in store.cardList"
      :key="index"
      class="card-character"
      :card="card"
    />
  </div>
</template>

<style lang="scss" scoped>
.cards-container {
  display: flex;
  flex-wrap: wrap;
}

.card-character {
  flex: 0 0 25%;
}
</style>
