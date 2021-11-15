<template>
  <router-link to="/order">
    <div @open="openCard" class="card">
      <img class="card__img" src="../assets/pizza.png" width="640" height="640" alt="pizza">
      <h2 class="card__title">{{ item.name }}</h2>
      <p class="card__price">price: <span class="card__price__num">{{ item.price }}</span></p>
    </div>
  </router-link>
</template>

<script>
export default {
  name: "Card",
  props: {
    item: {
      type: Object,
      required: true,
    }
  },
}
</script>

<style scoped>
.card {
  padding: 16px;
  border: 1px solid var(--border);
  border-radius: 2px;
}

.card__title,
.card__price {
  color: var(--text);
}
.card__price {
  margin: 0;
}
</style>