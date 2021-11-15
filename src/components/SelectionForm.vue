<template>
  <h1 class="title">Choose your pizza</h1>
  <div class="button-wrapper">
    <button class="button-arrow button-arrow--back" @click="goBack"></button>
    <div class="card-wrapper">
      <Card @click.prevent="openCard(item.id)" v-for="item in pizzaList" :item="item" :key="item.id"/>
    </div>
    <button class="button-arrow button-arrow--forward" @click="goForward"></button>
  </div>
</template>

<script>
import Card from "./Card";

export default {
  name: "SelectionForm",
  components: {Card},
  data() {
    return {
      page: 0,
    }
  },
  computed: {
    pizzaList() {
      return this.$root.pizzaList.slice(this.page, this.page + 6);
    },
  },
  methods: {
    openCard: function (value) {
      this.$router.push({
        path: '/order',
        query: {
          pizza: value
        },
      });
    },
    goBack: function () {
      if(this.page !== 0) {
        this.page = this.page - 6;
      }
    },
    goForward: function () {
      if(this.page + 6 < this.$root.pizzaList.length) {
        this.page = this.page + 6;
      }
    },
  },

}
</script>

<style scoped>
.title {
  text-align: center;
}

.card-wrapper {
  margin: 0 auto;
  padding: 0 64px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 16px;
}

.button-arrow {
  content: "";
  position: absolute;
  top: calc(50% - 36px / 2);
  height: 36px;
  width: 36px;
  background: url("../assets/arrow.svg");
  border: none;
  cursor: pointer;
}

.button-arrow--back {
  left: 0;
  transform: rotateY(180deg);
}
.button-arrow--forward {
  right: 0;
}

.button-wrapper{
  position: relative;
}
</style>