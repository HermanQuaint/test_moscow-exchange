<template>
  <h1 class="title">Make order</h1>
  <form class="form-order" v-if="pizzaCurrent">
    <div class="wrapper">
      <h2 class="form-order__pizza-name">{{  pizzaCurrent.name }}</h2>
      <p class="form-order__price">{{ pizzaCurrent.price }}</p>
    </div>
    <article class="wrapper">
      <h3 class="form-order__address-tittle">Address</h3>
      <div class="form-order__input-block">
        <label><input name="street" class="form-order__input-block__input" type="text" placeholder="street"></label>
        <label><input name="house" class="form-order__input-block__input" type="text" placeholder="house"></label>
        <label><input name="flat" class="form-order__input-block__input" type="text" placeholder="flat"></label>
        <button class="button button--form" type="submit">Make order</button>
      </div>
    </article>
  </form>
  <router-link class="form-error" to="/" v-if="!pizzaCurrent">Please choose pizza</router-link>
</template>

<script>
export default {
  name: "OrderingForm",
  computed: {
    pizzaCurrent() {
      let id = this.$route.query.pizza;
      return this.$root.pizzaList.find(item => item.id === Number(id));
    },
  },
}
</script>

<style scoped>
.form-order {
  display: grid;
  margin: 0 auto;
  max-width: 500px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 42px;
  margin-bottom: 24px;
}

.title {
  text-align: center;
}

.form-order__pizza-name,
.form-order__address-tittle {
  text-align: right;
  margin: 0;
}

.form-order__price {
  margin: 0;
}

.form-order__input-block {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-order__input-block__input {
  padding: 8px;
  font-size: 16px;
  border: 1px solid var(--border);
  border-radius: 2px;
}

.button--form {
  margin-top: 16px;
  align-self: end;
}

.form-error {
  display: block;
  margin-top: 64px;

  text-align: center;
  color: var(--text);
  font-size: 24px;
}
</style>