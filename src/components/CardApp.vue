<script>
export default {
  name: "CardApp",
  props: {
    card: Object,
  },
};
</script>

<template>
  <div class="card">
    <div class="bordo">
      <img :src="card.card_images[0].image_url" :alt="card.name" />
      <h2>{{ card.name }}</h2>
      <div class="species">{{ card.def }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  padding: 1rem;
  border: 2px solid brown;
  text-align: center;
}

img {
  // border-radius: 9em;
  max-width: 100%;
}
.bordo {
  padding: 0.3rem;
}
</style>
