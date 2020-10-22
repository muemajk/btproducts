<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(25em, 1fr));
  grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
  grid-gap: 1rem;
  min-height: 303px;
  height: auto;
  position: relative;
  width: 100%;
  padding: 0;
  padding-bottom: 5px;
  overflow-y: auto;
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
    grid-template-columns: repeat(auto-fit, minmax(25em, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
    grid-gap: 1rem;
    height: auto;
    min-height: 303px;
    position: relative;
    width: 100%;
  }
}
</style>
<template>
  <ul class="container">
    <li v-for="(blog, index) in blogs" :key="blog.title + index" class="item">
      <blogs :blog="blog" />
    </li>
  </ul>
</template>
<script>
export default {
  name: 'BlogStore',
  data() {
    return {
      blogs: [
        {
          title: 'Avocado growing',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Jim Ken',
        },
        {
          title: 'Investing in congo',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Muema James',
        },
        {
          title: 'Watermelon planting',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Muema Jim',
        },
        {
          title: 'Banana farms in machakos',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Muema Kennedy',
        },
        {
          title: 'Mango farms',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Muema Mutiso',
        },
        {
          title: 'Copper Mining',
          img: 'https://picsum.photos/200/300',
          short_description:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          author: 'Muema Ken',
        },
      ],
    }
  },
}
</script>
