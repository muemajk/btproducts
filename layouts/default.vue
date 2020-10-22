<style>
:root {
  --primary-color: rgb(201, 145, 37);
  --title-font: 'Prompt', sans-serif;
  --sub-title-font: 'Lemonada', cursive;
  --main-font: 'Open Sans Condensed', sans-serif;
  --secondary-color: rgb(225, 217, 198);
  --shadow-color: rgb(14, 22, 25);
  --logo-prominent-color: rgb(14, 22, 25);
}

html {
  font-family: var(--main-font);
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
@keyframes loadpage {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.main_container {
  display: grid;
  box-sizing: border-box;
  height: 100vh;
  width: 100%;
  grid-template-columns: 1fr;
  grid-gap: 1em;
  grid-template-areas:
    'navigation'
    'content'
    'footer';
  font-family: 'Abel', sans-serif;
  box-sizing: border-box;
  background-color: green;
  overflow-x: hidden;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.navigation {
  position: absolute;
  top: 0;
  width: 100%;
  height: auto;
  color: #000;
  grid-area: navigation;
  z-index: 999999999;
}

.content {
  animation: 3s ease-out 0s 1 loadpage;
  overflow-x: hidden;
  grid-area: content;
  position: relative;
  top: 0;
  height: 100%;
  overflow-y: auto;
  width: 100%;
  padding: 0;
}

.footer {
  grid-area: footer;
  border-top: 1px solid rgb(190, 187, 187);
  position: relative;
  width: 100%;
}

.moved {
  transform: translateX(80px);
  transition: 0.1s;
  transition-timing-function: ease-in-out;
}

.view {
  margin: 0 auto;
}
@media (min-width: 600px) {
  .navigation {
    top: 0;
    width: 100%;
    height: auto;
    color: #000;
  }
  .moved {
    transform: translateX(80px);
    transition: 0.1s;
    transition-timing-function: ease-in-out;
  }
}
@media (min-width: 1043px) {
  .navigation {
    top: 0;
    width: 100%;
    height: auto;
    color: #000;
  }
  .moved {
    transform: translateX(80px);
    transition: 0.1s;
    transition-timing-function: ease-in-out;
  }
}
</style>
<template>
  <div class="main_container">
    <header class="navigation">
      <navbar @navbaropened="navOpen" />
    </header>
    <main class="content" :class="{ moved: move_main }">
      <Nuxt />
    </main>
    <footer class="footer" :class="{ moved: move_main }">
      <foot />
    </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      move_main: false,
    }
  },
  methods: {
    navOpen(variable) {
      this.move_main = variable
    },
  },
}
</script>
