<template>
  <div class="px-3">
    <button
      class="uppercase text-4xl md:text-xl sm:text-xl xs:text-xl p-1 relative hover:text-orange flex cursor-pointer"
      @click.prevent="show"
    >
      <i class="fas fa-shopping-cart"></i>
      <div
        v-if="cart == true"
        class="h-3 flex justify-center w-3 absolute right-0 top-0 font-bold rounded-full bg-orange3 items-center text-black text-xxs text-center"
      >
        {{ cart_count }}
      </div>
    </button>
    <modal
      class="bg-black bg-opacity-50"
      name="modal-cart"
      :adaptive="true"
      :height="500"
      :scrollable="true"
      :width="320"
    >
      <div class="h-full mt-8 w-full py-6">
        <div class="flex justify-center flex-col items-center">
          <div
            v-if="cart == false"
            class="w-3/4 h-16 flex justify-center items-center text-red-600 text-base font-medium uppercase text-center rounded"
          >
            !! Your Cart is empty !!
          </div>
          <div
            v-if="cart == true"
            class="w-3/4 h-8 max-w-screen-md flex justify-center items-center text-green font-bold text-xs uppercase text-center rounded"
          >
            You have {{ cart_count }} items in Your cart
          </div>
          <div class="shadow-inner bg-white h-auto p-2">
            <div class="bg-white rounded w-full h-full">
              <ul class="divide-y-2 h-64">
                <vuescroll :ops="ops">
                  <!-- cart items  -->
                  <li
                    v-for="(item, index) in cart_items"
                    :key="index + item.id + item.name"
                    class="w-full flex flex-col m-1 px-3"
                  >
                    <div
                      class="flex p-1 h-20 m-1 border items-center rounded-sm justify-between"
                    >
                      <img
                        class="w-12 h-12"
                        :src="url + item.image"
                        alt="image"
                      />

                      <div
                        class="flex w-1/3 flex-col text-black justify-center"
                      >
                        <strong
                          class="font-body text-sm font-bold capitalize"
                          >{{ item.name }}</strong
                        >
                        <h1 class="font-body font-normal">
                          <span class="capitalize text-xxs">ksh</span>
                          {{ item.sale_price }}
                        </h1>
                      </div>
                      <div class="w-1/3 px-2 flex justify-evenly items-center">
                        <input
                          id=""
                          v-model="item.Amount"
                          class="rounded text-xs bg-gray-100 mr-3 w-12 border text-black py-2 px-1"
                          type="number"
                          name=""
                          @change="updateAmount(index)"
                        />
                        <button
                          class="text-2xl text-red-700"
                          @click="deletefromcart(index)"
                        >
                          <i class="far fa-times-circle"></i>
                        </button>
                      </div>
                    </div>
                  </li>
                </vuescroll>
              </ul>
            </div>
          </div>
          <div
            class="w-11/12 bg-gray-800 shadow rounded p-2 flex items-center flex-row"
          >
            <div
              class="w-1/2 rounded-l-lg text-left text-white font-body text-xl h-16 flex flex-col px-4 mr-2 justify-center"
            >
              <span class="text-xs font-light font-display">Total</span>
              <div>
                <span class="text-xxs capitalize">ksh</span> {{ totalprice }}
              </div>
            </div>
            <div
              class="w-1/2 rounded-r-lg text-left font-semibold text-xs h-16 font-body flex flex-col items-end m-1"
            >
              <button
                class="text-xxs mb-1 font-bold text-red-600 uppercase"
                @click="clearcart"
              >
                Clear cart
              </button>
              <button
                class="text-xs mb-1 capitalize text-orange"
                href=""
                @click.prevent="hide"
              >
                <router-link to="/store"
                  >Return to store<i class="fas fa-store"></i
                ></router-link>
              </button>
              <button
                class="text-center bg-green hover:text-black transition duration-300 ease-in-out uppercase font-semibold text-xs text-white px-3 py-1 hover:bg-orange rounded"
                href="/checkout"
                @click.prevent="hide"
              >
                <router-link to="/checkout"> checkout </router-link>
              </button>
            </div>
          </div>
        </div>
      </div>
    </modal>
  </div>
</template>

<script>
import vuescroll from 'vuescroll'
// import { API_URL } from '../../env.js'
// import AppStore from '../../store/Appstore.js'

// const appstore = AppStore
// let userstore = appstore.state.user;
// const accountstore = appstore.state.account
export default {
  components: {
    vuescroll,
  },
  data() {
    return {
      url: 'API_URL' + 'storage/',
      itemsincart: [],
      cart: true,
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
  computed: {
    totalprice() {
      return 0 // appstore.getters['account/total_cart_price']
    },
    cart_count() {
      return 0 //  appstore.getters['account/get_cart_length']
    },
    cart_items() {
      return 0 // accountstore.itemsincart
    },
  },
  mounted() {
    this.itemsincart = [] // accountstore.itemsincart
  },
  methods: {
    show() {
      this.$modal.show('modal-cart')
    },
    showLogin() {
      this.$modal.show('modal-login')
      this.$modal.hide('modal-cart')
    },
    hide() {
      this.$modal.hide('modal-cart')
    },
    deletefromcart(index) {
      // appstore.dispatch('account/removefromCartAsync', index)
    },
    updateAmount(index) {
      const itemcart = this.itemsincart[index]
      if (itemcart.Amount > 0 && itemcart.Amount < itemcart.stock) {
        // appstore.dispatch('account/updateAmountCartAsync')
      }
    },
    clearcart() {
      // appstore.dispatch('account/clearcartAsync')
    },
  },
}
</script>
