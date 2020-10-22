<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(9em, 1fr));
  grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
  grid-gap: 1rem;
  min-height: 303px;
  height: auto;
  position: relative;
  width: 100%;
  padding: 0;
  padding-bottom: 5px;
}

/* OTHER STYLES */

body {
  background-color: #3b404e;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
@media (min-width: 600px) {
  .container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(10em, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
    grid-gap: 3.5rem;
    height: auto;
    min-height: 303px;
    position: relative;
    width: 100%;
  }
}

@media (min-width: 1034px) {
  .container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(10em, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
    grid-gap: 2.5rem;
    height: auto;
    min-height: 303px;
    position: relative;
    width: 100%;
  }
}
</style>
<template>
  <ul class="container">
    <li
      v-for="(product, index) in products"
      :key="product.name + index"
      class="item"
    >
      <product :product="product" />
    </li>
  </ul>
</template>
<script>
export default {
  name: 'MiniStore',
  data() {
    return {
      products: [
        {
          name: 'Pineapples',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Mangos',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Green Grams',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Avocados',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Apples',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Bananas',
          img: 'https://picsum.photos/200/300',
        },
      ],
    }
  },
}
</script>
