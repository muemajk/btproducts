<style scoped>
@keyframes navbtnmove {
  0% {
    transform: rotate(-36deg);
    opacity: 0;
  }
  25% {
    transform: rotate(-72deg);
    opacity: 0;
  }
  50% {
    transform: rotate(-108deg);
    opacity: 0;
  }
  75% {
    transform: rotate(-144deg);
    opacity: 1;
  }
  100% {
    transform: rotate(-180deg);
  }
}

.navbar {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  border-bottom: 1px solid rgb(74, 72, 72);
  background-color: rgba(255, 255, 255, 0.107);
  text-shadow: 2px 2px #908e8e68;
  height: 80px;
  position: sticky;
  color: white;
}
.titlediv {
  margin: 0 auto;
  text-transform: uppercase;
  font-family: var(--title-font);
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  width: 100%;
  padding-left: 10px;
}

.titlediv span > p {
  color: white;
  position: absolute;
  bottom: 13px;
  font-size: 40px;
}
.linksul {
  display: flex;
  flex-direction: column;
  height: 102.3vh;
  max-height: 150vh;
  position: absolute;
  top: 0;
  left: 0;
  width: 80px;
  background-color: var(--primary-color);
  -moz-box-shadow: inset 0 0 10px #000000de;
  -webkit-box-shadow: inset 0 0 10px #000000de;
  box-shadow: inset 0 0 10px #000000de;
  transform: translateX(-80px);
  transition: 0.2s;
  transition-timing-function: ease-in-out;
}
.navbtn {
  position: relative;
  z-index: 5;
  overflow: hidden;
  top: 61%;
  right: -90px;
  background-color: white;
  border-radius: 30px;
  width: 55px;
  height: 55px;
  padding: 10px;
  outline: none;
  border: 0.5px solid #c6c6c688;
  -moz-box-shadow: 0 0 10px var(--shadow-color);
  -webkit-box-shadow: 0 0 10px var(--shadow-color);
  box-shadow: 0 0 10px var(--shadow-color);
  transition: 0.4s;
  transition-timing-function: ease-in-out;
}
.rotateImgbtn {
  animation-name: navbtnmove;
  animation-duration: 0.5s;
  animation-timing-function: linear;
  animation-fill-mode: forwards;
}
.linksul button:active + :focus > img {
  transform: rotate(0deg);
}

.linksul button:focus {
  -moz-box-shadow: 0 0 10px rgb(245, 169, 69);
  -webkit-box-shadow: 0 0 10px rgb(245, 169, 69);
  box-shadow: 0 0 10px rgb(245, 169, 69);
}
.linksul button:active .linksul {
  background-color: rgb(245, 169, 69);
}
.navbtn:focus .linksul {
  background-color: rgb(245, 169, 69);
  transform: translateX(80px);
  transition: 0.4s;
}

.linksul li {
  padding-top: 50%;
  margin: 0 auto;
  transition: 0.3s;
  transition-timing-function: ease-in-out;
}
.linknames {
  font-size: 15px;
  color: white;
  font-weight: 700;
}
.sideavopen {
  transform: translateX(0px);
  transition: 0.2s;
  transition-timing-function: ease-in-out;
}
.sideavopen li {
  transition: 0.3s;
  transition-timing-function: ease-in-out;
}
.sideavopen > .navbtn {
  right: -10px;
  -moz-box-shadow: 0 0 10px #000;
  -webkit-box-shadow: 0 0 10px #000;
  box-shadow: 0 0 10px #000;
}
.link {
  padding: 0 auto;
}
.accountdiv {
  position: absolute;
  bottom: 20%;
  border-top: 1px solid white;
}
.accountlinks {
  margin: 2px 0;
  width: 100%;
  background-color: var(--logo-prominent-color);
  color: rgb(255, 255, 255);
}
.logo {
  background-image: url('../../assets/logos/btproducts.png');
  background-size: cover;
  background-position: center;
  width: 65px;
  height: 65px;
  margin: 5px;
}
@media (min-width: 600px) {
  .navbar {
    width: 100%;
    display: flex;
    justify-content: flex-start;
    border-bottom: 1px solid rgb(74, 72, 72);
    background-color: transparent;
    text-shadow: 2px 2px #908e8e68;
    height: 80px;
    position: sticky;
    color: white;
  }
  .titlediv {
    margin: 0 auto;
    text-transform: uppercase;
    font-family: var(--title-font);
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    width: 100%;
    padding-left: 10px;
  }

  .titlediv span > p {
    color: white;
    position: absolute;
    bottom: 13px;
    font-size: 40px;
  }
  .linksul {
    display: flex;
    flex-direction: column;
    height: 120.3vh;
    max-height: 150vh;
    position: absolute;
    top: 0;
    left: 0;
    width: 80px;
    background-color: var(--primary-color);
    -moz-box-shadow: inset 0 0 10px #000000de;
    -webkit-box-shadow: inset 0 0 10px #000000de;
    box-shadow: inset 0 0 10px #000000de;
    transform: translateX(-80px);
    transition: 0.2s;
    transition-timing-function: ease-in-out;
  }
  .navbtn {
    position: relative;
    z-index: 5;
    overflow: hidden;
    top: 51%;
    right: -90px;
    background-color: white;
    border-radius: 30px;
    width: 55px;
    height: 55px;
    padding: 10px;
    outline: none;
    border: 0.5px solid #c6c6c688;
    -moz-box-shadow: 0 0 10px var(--shadow-color);
    -webkit-box-shadow: 0 0 10px var(--shadow-color);
    box-shadow: 0 0 10px var(--shadow-color);
    transition: 0.4s;
    transition-timing-function: ease-in-out;
  }
  .rotateImgbtn {
    animation-name: navbtnmove;
    animation-duration: 0.5s;
    animation-timing-function: linear;
    animation-fill-mode: forwards;
  }
  .linksul button:active + :focus > img {
    transform: rotate(0deg);
  }

  .linksul button:focus {
    -moz-box-shadow: 0 0 10px rgb(245, 169, 69);
    -webkit-box-shadow: 0 0 10px rgb(245, 169, 69);
    box-shadow: 0 0 10px rgb(245, 169, 69);
  }
  .linksul button:active .linksul {
    background-color: rgb(245, 169, 69);
  }
  .navbtn:focus .linksul {
    background-color: rgb(245, 169, 69);
    transform: translateX(80px);
    transition: 0.4s;
  }

  .linksul li {
    padding-top: 50%;
    margin: 0 auto;
    transition: 0.3s;
    transition-timing-function: ease-in-out;
  }
  .linknames {
    font-size: 15px;
    color: white;
    font-weight: 700;
  }
  .sideavopen {
    transform: translateX(0px);
    transition: 0.2s;
    transition-timing-function: ease-in-out;
  }
  .sideavopen li {
    transition: 0.3s;
    transition-timing-function: ease-in-out;
  }
  .sideavopen > .navbtn {
    right: -10px;
    -moz-box-shadow: 0 0 10px #000;
    -webkit-box-shadow: 0 0 10px #000;
    box-shadow: 0 0 10px #000;
  }
  .link {
    padding: 0 auto;
  }
  .accountdiv {
    position: absolute;
    bottom: 30%;
    border-top: 1px solid white;
  }
  .accountlinks {
    margin: 2px 0;
    width: 100%;
    background-color: var(--logo-prominent-color);
    color: rgb(255, 255, 255);
  }
  .logo {
    background-image: url('../../assets/logos/btproducts.png');
    background-size: cover;
    background-position: center;
    width: 65px;
    height: 65px;
    margin: 5px;
  }
}
@media (min-width: 1083px) {
  .navbar {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    color: white;
    padding: 10px;
    height: auto;
    min-height: 60px;
    border: none;
    overflow: hidden;
    border-bottom: 1px solid rgb(239, 237, 237);

    background-color: transparent;
    text-shadow: 2px 2px #908e8e68;
  }
  .linksul {
    display: flex;
    flex-direction: row;
    height: 100%;
    position: relative;
    width: 40%;
    font-size: 12px;
    top: 0;
    left: 0;
    background-color: transparent;
    -moz-box-shadow: none;
    -webkit-box-shadow: none;
    box-shadow: none;
    border-radius: 0;
    transform: translate(0px);
  }
  .accountdiv {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    left: 0px;
    border: 0px;
    padding-left: 30px;
  }
  .navbtn {
    display: none;
  }
  .linksul li {
    padding-top: 10px;
    margin-left: 40px;
  }
  .linksul li:hover {
    color: rgb(245, 169, 69);
  }
  .linknames {
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    color: white;
  }
  .imagelinks {
    display: none;
  }
  .titlediv {
    margin: 0;
  }

  .accountlinks {
    margin: 2px;
    width: 80px;
    background-color: transparent;
    color: rgb(0, 0, 0);
    font-weight: 700;
    border: 1px solid var(--secondary-color);
    border-radius: 20px;
    padding: 2px;
    transition: 0.3s;
  }
  .accountlinks:hover {
    background-color: var(--primary-color);
    color: #fff;
    transition: 0.3s;
  }
  .titlediv {
    display: flex;
    flex-direction: row;
  }
  .titlediv span > p {
    color: white;
  }
  .logo {
    background-image: url('../../assets/logos/btproducts.png');
    background-size: cover;
    background-position: center;
    width: 45px;
    height: 45px;
  }
}
@media (min-width: 1292px) {
  .navbar {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    color: white;
    padding: 10px;
    height: auto;
    min-height: 60px;
    border: none;
    overflow: hidden;
    border-bottom: 1px solid rgb(239, 237, 237);
    background-color: transparent;
    text-shadow: 2px 2px #908e8e68;
  }
  .linksul {
    display: flex;
    flex-direction: row;
    height: 100%;
    position: relative;
    width: 40%;
    font-size: 12px;
    top: 0;
    left: 0;
    background-color: transparent;
    -moz-box-shadow: none;
    -webkit-box-shadow: none;
    box-shadow: none;
    border-radius: 0;
    transform: translate(0px);
  }
  .accountdiv {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    position: relative;
    left: 0px;
    border: 0px;
    padding-left: 30px;
  }
  .navbtn {
    display: none;
  }
  .linksul li {
    padding-top: 10px;
    margin-left: 40px;
  }
  .linksul li:hover {
    color: rgb(245, 169, 69);
  }
  .linknames {
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    color: white;
  }
  .imagelinks {
    display: none;
  }
  .titlediv {
    margin: 0;
  }

  .accountlinks {
    margin: 2px;
    width: 80px;
    background-color: transparent;
    color: white;
    font-weight: 700;
    border: 1px solid var(--secondary-color);
    border-radius: 20px;
    padding: 2px;
    transition: 0.3s;
  }
  .accountlinks:hover {
    background-color: var(--primary-color);
    color: #fff;
    transition: 0.3s;
  }
  .titlediv {
    display: flex;
    flex-direction: row;
  }
  .titlediv span > p {
    color: white;
  }
  .logo {
    background-image: url('../../assets/logos/btproducts.png');
    background-size: cover;
    background-position: center;
    width: 45px;
    height: 45px;
  }
}
</style>
<template>
  <nav class="navbar">
    <div class="titlediv ext-white font-style">
      <div class="logo"></div>
      <span>
        <p class="text-black font-lg font-body">
          <a href="#">BT</a>
          Products
        </p></span
      >
    </div>
    <ul class="linksul" :class="{ sideavopen: opened }">
      <button
        class="navbtn"
        :class="{ rotateImgbtn: opened }"
        @click="navopened"
      >
        <img
          class="imagelinks"
          src="../../assets/img/leftarrows.png"
          width="35px"
          height="35px"
        />
      </button>
      <li
        class="mr-4 uppercase text-base font-body font-semibold hover:text-orange"
      >
        <NuxtLink class="link" to="/">
          <img
            class="imagelinks"
            src="../../assets/img/dark_home.png"
            width="45px"
            height="35px"
          />
          <p class="linknames">home</p>
        </NuxtLink>
      </li>
      <li
        class="mr-4 uppercase text-base font-body font-semibold hover:text-orange"
      >
        <NuxtLink class="link" to="/blog">
          <img
            class="imagelinks"
            src="../../assets/img/blogging.png"
            width="45px"
            height="35px"
          />
          <p class="linknames">Blog</p>
        </NuxtLink>
      </li>
      <li
        class="mr-4 uppercase text-base font-body font-semibold hover:text-orange"
      >
        <NuxtLink class="link" to="/store">
          <img
            class="imagelinks"
            src="../../assets/img/store.png"
            width="45px"
            height="35px"
          />
          <p class="linknames">Store</p>
        </NuxtLink>
      </li>
      <li
        class="mr-4 uppercase text-base font-body font-semibold hover:text-orange"
      >
        <NuxtLink class="link" to="/profile">
          <img
            class="imagelinks"
            src="../../assets/img/user.png"
            width="45px"
            height="35px"
          />
          <p class="linknames">Profile</p>
        </NuxtLink>
      </li>
      <div class="accountdiv">
        <button class="accountlinks">
          <NuxtLink to="/authenticate">Login</NuxtLink>
        </button>
        <button class="accountlinks">
          <NuxtLink to="/authenticate">Register</NuxtLink>
        </button>
      </div>
      <li
        v-if="get_user"
        class="mr-4 capitalize text-xl text-orange font-body font-semibold"
      >
        <router-link to="/Account" class="flex items-center">
          <p class="font-body text-xxs mr-1">{{ get_user.name }}</p>
          <i class="fas fa-user-circle"></i
        ></router-link>
      </li>
      <li v-else class="mr-4 uppercase text-sm font-body font-semibold flex">
        <!-- <ModalLogin />
        <ModalRegister />-->
      </li>
      <li
        class="uppercase text-base font-body font-semibold hover:text-orange text-green"
      >
        <!--<ModalCart />-->
      </li>
    </ul>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      opened: false,
      get_user: null,
    }
  },
  methods: {
    navopened() {
      this.opened = !this.opened
      this.$emit('navbaropened', this.opened)
    },
  },
}
</script>
