<template>
  <div class="tracking-normal">
    <button
      to="/#login"
      class="text-copy-primary mx-1 uppercase hover:text-orange cursor-pointer underline"
      @click.prevent="show"
    >
      Login
    </button>
    <modal
      name="modal-login"
      :adaptive="true"
      :height="440"
      :width="300"
      @opened="opened"
    >
      <div class="px-10 py-8 text-black">
        <h2 class="mb-4 uppercase tracking-wide text-xl">Login</h2>
        <form>
          <div class="form-group mb-4">
            <label
              for="email"
              class="block font-normal uppercase tracking-wide text-xs mb-1"
              >Email</label
            >
            <input
              id="email"
              ref="email"
              v-model="email"
              type="email"
              name="email"
              class="border px-4 py-2 w-full rounded bg-gray-200"
              @keydown.shift.tab.prevent=""
            />
          </div>
          <div class="form-group mb-4 relative">
            <label
              for="password"
              class="block font-normal uppercase tracking-wide text-xs mb-1"
              >Password</label
            >
            <input
              id="password"
              v-model="password"
              type="password"
              name="password"
              class="border px-4 py-2 w-full rounded bg-gray-200"
            />
            <button
              v-if="showPassword == null"
              class="absolute right-0 py-2 px-2 text-lg text-gray-500"
              @click="showpassword"
            >
              <i class="far fa-eye"></i>
            </button>
            <button
              v-if="showPassword == true"
              class="absolute right-0 py-2 px-2 text-lg text-gray-500"
              @click="hidepassword"
            >
              <i class="far fa-eye-slash"></i>
            </button>
          </div>
          <div class="form-group mb-4">
            <button
              class="bg-green hover:bg-green3 text-white px-4 py-2 rounded w-full"
              @click="login"
            >
              Login
            </button>
          </div>
        </form>
        <div class="text-sm font-normal text-center">
          <p>
            Don't have an account?
            <button
              to="#"
              class="text-blue-600 hover:text-blue-800"
              @click.prevent="showRegister"
              @keydown.tab.exact.prevent=""
            >
              Register
            </button>
          </p>
        </div>
      </div>
    </modal>
  </div>
</template>

<script>
// import { API_URL, clientId, clientSecret } from '../../env.js'
// import AppStore from '../../store/Appstore.js'

// import { togglepassword } from '../../computed/togglepassword.js'
// const appstore = AppStore
export default {
  name: 'ModalLogin',
  data() {
    return {
      password: null,
      email: null,
      showPassword: null,
    }
  },

  methods: {
    showpassword() {
      event.preventDefault()
      // togglepassword()
      this.showPassword = true
    },
    hidepassword() {
      event.preventDefault()
      // togglepassword()
      this.showPassword = null
    },
    show() {
      this.$modal.show('modal-login')
    },
    showRegister() {
      this.$modal.show('modal-register')
      this.$modal.hide('modal-login')
    },
    opened() {
      this.$refs.email.focus()
    },
    hide() {
      this.$modal.hide('modal-login')
    },
    login() {
      event.preventDefault()
      const email = this.email
      const password = this.password

      if (email && password) {
        const formdata = new FormData()
        formdata.append('grant_type', 'password')
        formdata.append('client_id', 0)
        formdata.append('client_secret', 0)
        formdata.append('email', email)
        formdata.append('password', password)
        formdata.append('scope', '')

        this.$http
          .post('jhljhljh' + 'api/loginuser', formdata)
          .then((response) => {
            this.setUser(response)
          })
          .catch(function (error) {
            const notify = {
              message: error.response.data,
              status: 'fail',
              code: error.response.status,
            }
            alert(notify)
            // appstore.dispatch('account/setNotificationAsync', notify)
          })
      }
    },
    setUser(data) {
      if (data.status === 200) {
        // appstore.dispatch('user/setAuthenticationAsync', data.data)
      }
    },
  },
}
</script>
