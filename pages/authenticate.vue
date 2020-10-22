<style scoped>
@keyframes animate_registration {
  0% {
    opacity: 0;
  }
  25% {
    opacity: 0.25;
  }
  50% {
    opacity: 0.5;
  }
  75% {
    opacity: 0.75;
  }
  100% {
    opacity: 1;
  }
}
.displayform {
  animation-name: animate_registration;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-fill-mode: ease;
  display: none;
}
.authenticate {
  margin: 2em auto;
  width: 100%;
  height: 100vh;
  font-family: var(--main-font);
  font-size: 30px;
  padding: 1em 2em;
}
.authenticate form {
  height: 70vh;
}
.form-group {
  margin: 5px 0;
  position: relative;
  height: 100px;
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid;
  overflow-x: hidden;
}
.form-group input {
  width: 100%;
  height: 100%;
  outline: none;
  padding-top: 20px;
  font-size: 14px;
  border-bottom-color: var(--logo-prominent-color);
}
.form-group input:focus + .form-label .content-name, .form-group input:valid + .form-label .content-name{
  transform: translateY(-70%);
  color: var(--primary-color);
}
.form-group input:focus + .form-label::after, .form-group input:valid + .form-label::after {
  transform: translateX(0);
  transition: all 0.3s ease-in-out;
}
.form-label {
  position: absolute;
  bottom: 0px;
  width: 100%;
  height: 100%;
  left: 0px;
  pointer-events: none;
  border: none;
}
.form-label::after {
  content: "";
  bottom: -3px;
  left: 0px;
  height: 100%;
  width: 100%;
  position: absolute;
  border-bottom: 3px solid var(--primary-color);
  transform: translateX(-100%);
}
.form-radio-group {
  margin: 30px auto;
}
.changesystem button {
  color: blue;
}
.form-action-group {
  float: right;
}
.form-action-group button {
  background-color: var(--primary-color);
  min-width: 100px;
  width: auto;
  padding: 2px;
  font-weight: bold;
  color: white;
}
.registerform {
  display: block;
}
.content-name {
  position: absolute;
  bottom: 2px;
  transition: all 0.3s ease;
}
@media (min-width: 600px) {
  .authenticate {
    width: 100%;
    font-size: 30px;
    width: 80%;
    padding: 1em 1em;
  }
  .form-group {
    height: 100px;
  }
}
@media (min-width: 1034px) {
  .authenticate {
    margin: 5em auto;
    width: 30%;
    font-size: 20px;
  }
  .form-group {
    height: 50px;
  }

}
</style>
<template>
  <div class="authenticate">
    <form>
      <div
        v-if="isregister"
        class="form-group registerform"
        :class="{ displayform: isregister }"
      >
        <input
          id="name"
          v-model="name"
          type="text"
          class="name"
          name="name"
          required
        >
        <label class="form-label content-name" for="name"><p class=" content-name">Name</p></label>
      </div>
      <div class="form-group loginform">
        <input
          id="email"
          v-model="email"
          type="email"
          class="email"
          name="Email"
          required
        >
        <label class="form-label content-name" for="email"><p class=" content-name">Email address</p></label>
      </div>
      <div
        v-if="isregister"
        class="form-group registerform"
        :class="{ displayform: isregister }"
      >
        <input
          id="location"
          v-model="location"
          type="text"
          class="location"
          name="location"
          required
        >
        <label class="form-label content-name" for="location"><p class=" content-name">Location</p></label>
      </div>
      <div class="form-group loginform">
        <input
          id="password"
          v-model="password"
          type="text"
          class="password"
          name="password"
          required
        >
        <label class="form-label" for="password"><p class=" content-name">Password</p></label>
      </div>
      <div
        v-if="isregister"
        class="form-group registerform"
        :class="{ displayform: isregister }"
      >
        <input
          id="conpass"
          v-model="conpass"
          type="password"
          class="conpass"
          name="conpass"
          required
        >
        <label class="form-label" for="conpass"><p class=" content-name">Confirm password</p></label>
      </div>
      <div
        v-if="isregister"
        class="form-radio-group registerform"
        :class="{ displayform: isregister }"
      >
        <input id="gender_male" v-model="gender" type="radio" value="male" class="gender">
        <label for="gender_male">Male</label>
        <input id="gender_female" v-model="gender" type="radio" value="female" class="gender">
        <label for="gender_female">Female</label>
      </div>
      <div class="form-action-group">
        <button v-if="isregister">
          Register
        </button>
        <button v-else>
          Login
        </button>
      </div>
    </form>
    <div v-if="isregister" class="changesystem">
      <p>
        Already have an account?
        <button @click="isregister = false">
          Login
        </button>
      </p>
    </div>
    <div v-else class="changesystem">
      <p>
        Don't have an account?
        <button @click="isregister = !isregister">
          Register
        </button>
      </p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Authentication',
  data () {
    return {
      isregister: true,
      name: null,
      email: null,
      location: null,
      password: null,
      conpass: null,
      gender: null
    }
  },
  methods: {
    register () {
      if (this.isregister === true) {

      }
    }
  }
}
</script>

