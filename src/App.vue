<template>
  <div class="container">
    <header>
      <router-link to="/">
        <img class="logo" alt="logo Fizza" src="./assets/logo.svg">
      </router-link>
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      pizzaList: [
        {
          id: 1,
          name: 'four cheese',
          price: 400,
        },
        {
          id: 2,
          name: 'mexican',
          price: 500,
        },
        {
          id: 3,
          name: 'aerobic',
          price: 350,
        },
        {
          id: 4,
          name: 'tropic',
          price: 470,
        },
        {
          id: 5,
          name: 'pipe-pupa',
          price: 999,
        },
        {
          id: 6,
          name: 'margarita',
          price: 430,
        },
        {
          id: 7,
          name: 'olive',
          price: 510,
        },
      ],
    }
  },
}
</script>

<style>
:root {
  --text: #000000;

  --border: #F0272A;
  --color1: #F1561C;
  --color2: #F2850E;
  --button: #F4B400;

  --background: #FCFCFC;
}

*, *:before, *:after {
  box-sizing: border-box
}

img {
  max-width: 100%;
  height: auto;
}

a {
  text-decoration: none;
}

#app {
  margin: 0;
  padding: 0;

  font-family: 'Roboto', sans-serif;
  font-size: 16px;
  line-height: 24px;
  font-weight: 400;
  color: var(--text);

  background-color: var(--background);
}

.container {
  min-width: 768px;
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 20px;
}

.button {
  display: inline-block;
  padding: 10px 20px;

  font-weight: 700;

  border: none;
  border-radius: 2px;
  background: var(--button);
  cursor: pointer;
}

.logo {
  height: 50px;
}
</style>
