<style scoped>
.errordiv {
  border-bottom: 2px solid rgba(251, 45, 45, 0.842);
  color: red;
  width: 95%;
  height: 100%;
  background-color: rgba(250, 179, 179, 0.397);
  margin: 10px;
  font-size: 16px;
  position: relative;
  left: 0;
  padding-left: 0px;
}
</style>
<template>
  <div class="normal-case tracking-normal">
    <a
      to="/#register"
      class="text-copy-primary uppercase hover:text-orange cursor-pointer underline"
      @click.prevent="show"
      >Register</a
    >
    <modal
      name="modal-register"
      :adaptive="true"
      :height="500"
      :width="320"
      :scrollable="true"
      @opened="opened"
    >
      <vuescroll>
        <div class="px-10 pt-10 text-black">
          <h2 class="mb-1 uppercase tracking-wide text-xl">Register</h2>
          <form>
            <div class="form-group mb-1" :class="{ errordiv: errorname }">
              <label
                for="name"
                class="block font-normal uppercase tracking-wide text-xs mb-1"
                >Name</label
              >
              <input
                id="name"
                ref="name"
                v-model="name"
                type="name"
                class="border px-4 py-2 w-full rounded bg-gray-200"
                @keydown.shift.tab.prevent=""
              />
            </div>
            <div class="form-group mb-1" :class="{ errordiv: errortele }">
              <label
                for="number"
                class="block font-normal uppercase tracking-wide text-xs mb-1"
                >Phone Number</label
              >
              <input
                id="number"
                ref="number"
                v-model="number"
                type="number"
                class="border px-4 py-2 w-full rounded bg-gray-200"
                @keydown.shift.tab.prevent=""
              />
            </div>
            <div class="form-group mb-1" :class="{ errordiv: erroremail }">
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
                class="border px-4 py-2 w-full rounded bg-gray-200"
                @keydown.shift.tab.prevent=""
              />
            </div>
            <div
              class="relative form-group mb-1"
              :class="{ errordiv: errorpass }"
            >
              <label
                for="password"
                class="block font-normal uppercase tracking-wide text-xs mb-1"
                >Password</label
              >
              <input
                id="password"
                v-model="password"
                type="password"
                class="border px-4 py-2 w-full rounded bg-gray-200"
              />

              <button
                class="absolute right-0 py-2 px-2 text-lg text-gray-500"
                @click="showpassword"
              >
                <i class="far fa-eye"></i>
              </button>
              <button
                v-if="showPassword === true"
                class="absolute right-0 py-2 px-2 text-lg text-gray-500"
                @click="hidepassword"
              >
                <i class="far fa-eye-slash"></i>
              </button>
            </div>
            <div class="form-group mb-4" :class="{ errordiv: errorcon }">
              <label
                for="confirm_password"
                class="block font-normal uppercase tracking-wide text-xs mb-1"
                >Confirm Password</label
              >
              <input
                id="confirm_password"
                v-model="confirm_password"
                type="password"
                class="border px-4 py-2 w-full rounded bg-gray-200"
              />
            </div>
            <div class="form-group mb-1" :class="{ errordiv: erroraddress }">
              <label
                for="address"
                class="block font-normal uppercase tracking-wide text-xs mb-1"
                >Address</label
              >
              <input
                id="address"
                ref="name"
                v-model="address"
                type="text"
                class="border px-4 py-2 w-full rounded bg-gray-200"
                @keydown.shift.tab.prevent=""
              />
              <div class="form-group mb-1" :class="{ errordiv: errorloc }">
                <label
                  for="location"
                  class="flex font-normal uppercase tracking-wide text-xxs mb-1"
                  >location</label
                >
                <select
                  id="location"
                  v-model="location"
                  class="flex appearance-none w-full bg-white shadow hover:border-gray-500 px-4 py-2 pr-8 rounded leading-tight focus:outline-none focus:shadow"
                >
                  <option value="Kitengela">Kitengela</option>
                  <option value="Mlolongo">Mlolongo</option>
                  <option value="Athi River">Athi River</option>
                  <option value="Nairobi">Nairobi</option>
                </select>
              </div>
            </div>
          </form>
          <div class="form-group mb-1">
            <button
              class="bg-green hover:bg-green3 text-white px-4 py-2 rounded w-full"
              @click="submitform()"
            >
              Register
            </button>
          </div>
          <div class="text-sm font-normal text-center">
            <p>
              Already have an account?
              <a
                to="#"
                class="text-blue-600 hover:text-blue-800"
                @click.prevent="showLogin"
                @keydown.tab.exact.prevent=""
                >Login</a
              >
            </p>
          </div>
        </div>
      </vuescroll>
    </modal>
  </div>
</template>

<script>
import vuescroll from 'vuescroll'
// import AppStore from '../../store/Appstore.js'
// import { API_URL, clientId, clientSecret } from '../../env.js'
// import { togglepassword } from '../../computed/togglepassword.js'
// const appstore = AppStore
// const userstore = appstore.state.user
export default {
  components: {
    vuescroll,
  },
  data() {
    return {
      showPassword: null,
      name: null,
      number: null,
      email: null,
      password: null,
      confirm_password: null,
      address: null,
      location: null,
      errorloc: false,
      erroraddress: false,
      errorname: false,
      errorpass: false,
      errorregfail: false,
      errormismatch: false,
      errortele: false,
      erroremail: false,
      errorcon: false,
      ops: {
        vuescroll: {},
        scrollPanel: {
          initialScrollY: false,
          initialScrollX: false,
          scrollingX: false,
          scrollingY: true,
          speed: 300,
          easing: undefined,
          verticalNativeBarPos: 'right',
        },
        rail: {
          background: '#F7FAFC',
          opacity: 1,
          size: '8px',
          specifyBorderRadius: false,
          gutterOfEnds: '1px',
          gutterOfSide: '1px',
          keepShow: false,
        },
        bar: {
          enable: true,
          background: '#CBD5E0',
          opacity: 1,
          step: 180,
          mousedownStep: 30,
        },
      },
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
      this.$modal.show('modal-register')
    },
    showLogin() {
      this.$modal.show('modal-login')
      this.$modal.hide('modal-register')
    },
    opened() {
      this.$refs.name.focus()
    },
    hide() {
      this.$modal.hide('modal-register')
    },
    namevalidator() {
      event.preventDefault()
      if (this.name === null) {
        this.errorname = true
        return false
      } else {
        return false
      }
    },
    passwordvalidator() {
      event.preventDefault()
      const myRe = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{6,20}$/

      if (this.password === null) {
        this.errorpass = true
        return false
      } else if (myRe.exec(this.password) === null) {
        this.errorpass = true
        this.errorregfail = true
        return false
      } else if (this.confirm_password === null) {
        this.errorpass = true
        this.errormismatch = true
        return false
      } else if (this.confirm_password !== this.password) {
        this.errorpass = true
        this.errormismatch = true
        return false
      }
      return true
    },

    emailvalidator() {
      event.preventDefault()
      if (this.email === null) {
        this.erroremail = true
        return false
      } else {
        return true
      }
    },
    telephonevalidator() {
      event.preventDefault()
      if (this.number === null) {
        this.errortele = true
        return false
      } else {
        return false
      }
    },
    addressvalidate() {
      event.preventDefault()
      if (this.address === null) {
        this.erroraddress = true
        return false
      } else {
        return true
      }
    },
    locationvalidate() {
      event.preventDefault()
      if (this.country === null) {
        this.errorcon = true
        return false
      } else {
        return true
      }
    },
    submitform() {
      event.preventDefault()
      if (
        this.locationvalidate() === false &&
        this.addressvalidate() === false &&
        this.telephonevalidator() === false &&
        this.emailvalidator() === false &&
        this.passwordvalidator() === false &&
        this.namevalidator() === false
      ) {
        return false
      } else {
        const formdata = new FormData()
        formdata.append('name', this.name)
        formdata.append('email', this.email)
        formdata.append('password', this.password)
        formdata.append('confirmed_password', this.confirm_password)
        formdata.append('address', this.address)
        formdata.append('location', this.location)
        formdata.append('telephone', this.number)
        formdata.append('grant_type', 'password')
        formdata.append('client_id', 0)
        formdata.append('client_secret', 0)
        formdata.append('scope', '')
        this.$http
          .post('API_URL' + 'api/register', formdata)
          .then((response) => {
            this.userregistration(response)
          })
          .catch(function (err) {
            let response
            if (err.response.status === 422) {
              if (err.response.data.errors.email) {
                response = {
                  status: 'fail',
                  message: err.response.data.errors.email[0],
                  code: 422,
                }
              } else if (err.response.data.errors.password) {
                response = {
                  status: 'fail',
                  message: err.response.data.errors.password[0],
                  code: 422,
                }
              } else {
                response = {
                  status: 'fail',
                  message: err.response.data.message,
                  code: 422,
                }
              }
              alert(response)
              // appstore.dispatch('account/setNotificationAsync', response)
            } else {
              const response = {
                status: 'fail',
                message: 'failed registration',
                code: 403,
              }
              alert(response)
              // appstore.dispatch('account/setNotificationAsync', response)
            }
          })
      }
    },
    userregistration(data) {
      if (data.status === 200) {
        /* if (userstore.user === null) {
          appstore.dispatch('account/setNotificationAsync', data.data)
          this.$modal.hide('modal-register')
        } */
      }
    },
  },
}
</script>
