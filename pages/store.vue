<style scoped>
.batchcontainer {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(12em, 1fr));
  grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
  grid-gap: 2rem;
  min-height: 303px;
  height: auto;
  max-height: 100vh;
  position: relative;
  width: 100%;
  overflow-y: auto;
}
.store {
  display: flex;
  width: 100%;
  grid-area: store;
}
.category {
  grid-area: category;
}
.storepage {
  width: 100%;
  height: auto;
  display: grid;
  grid-template-columns: 20% 80%;
  grid-template-areas: 'category store';
  padding: 1rem;
  padding-bottom: 5px;
  padding-top: 5rem;
}
.category button {
  background-color: var(--logo-prominent-color);
  color: white;
  font-family: var(--main-font);
  border-radius: 2px;
}
.category button:hover {
  background-color: var(--primary-color);
}
.category button:active,
.category button:focus {
  background-color: var(--primary-color);
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
  .batchcontainer {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(10em, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(15em, 1fr));
    grid-gap: 3rem;
    padding: 2rem;
    height: auto;
    min-height: 303px;
    position: relative;
    width: 100%;
  }
  .storepage {
    width: 100%;
    height: auto;
    display: grid;
    grid-template-columns: 20% 80%;
    grid-template-areas: 'category store';
    padding: 1rem;
    padding-bottom: 5px;
    padding-top: 2rem;
  }
  .category {
    grid-area: category;
  }
  .category button {
    background-color: var(--logo-prominent-color);
    color: white;
    font-family: var(--main-font);
    border-radius: 2px;
    -moz-box-shadow: inset 0 0 10px #000000de;
    -webkit-box-shadow: inset 0 0 10px #000000de;
    box-shadow: inset 0 0 10px #000000de;
  }
  .category button:hover {
    background-color: var(--primary-color);
  }
  .category button:active,
  .category button:focus {
    background-color: var(--primary-color);
  }
}
</style>
<template>
  <div class="flex items-center bg-white flex-col overflow-x-hidden w-full">
    <div
      class="flex justify-center xl:w-1/2 lg:w-1/2 md:w-1/2 sm:w-3/4 xs:w-full"
    >
      <!--<store-search @searcheddata="searchedbatch" />-->
    </div>
    <div v-if="clickbatch == null" class="w-full">
      <div class="storepage">
        <div
          class="category xl:col-span-1 px-2 lg:col-span-1 md:col-span-6 sm:col-span-6 xs:col-span-6"
        >
          <h1 class="capitalize font-body px-1 text-xs">Sort By category</h1>
          <ul class="category_list flex w-full flex-wrap px-1 justify-center">
            <li
              v-if="category_previous_page"
              class="m-1 hover:bg-green3 bg-gray-100 hover:text-white flex rounded"
            >
              <button
                class="flex flex-col w-20 h-20 justify-center items-center"
                @click="previouscategory()"
              >
                <!--<img class="w-6 h-6" :src="url + category.category_image" alt="" />-->
                <h2 class="md:text-sm sm:text-xs xs:text-xxs text-center">
                  <strong>BACK</strong>
                </h2>
              </button>
            </li>
            <li
              class="m-1 hover:bg-green3 bg-gray-100 hover:text-white flex rounded"
            >
              <button
                class="flex flex-col w-20 h-20 justify-center items-center"
                @click="loadBatches()"
              >
                <!--<img class="w-6 h-6" :src="url + category.category_image" alt="" />-->
                <h2 class="md:text-sm sm:text-xs xs:text-xxs text-center">
                  <strong>ALL</strong>
                </h2>
              </button>
            </li>
            <li
              v-for="(cate, index) in categories"
              :key="index + cate.id"
              class="m-1 hover:bg-orange bg-gray-100 border-gray-400 rounded"
            >
              <button
                class="flex flex-col w-20 h-20 p-2 justify-center items-center"
                @click="loadcategorybathes(index)"
              >
                <img class="h-16" :src="url + cate.category_image" alt="" />
                <h2 class="md:text-xs sm:text-xs xs:text-xxs text-center">
                  {{ cate.category_name }}
                </h2>
              </button>
            </li>
            <li
              class="m-1 hover:bg-green3 bg-gray-100 hover:text-white flex rounded"
            >
              <button
                class="flex flex-col w-20 h-20 justify-center items-center"
                @click="morecategory()"
              >
                <!--<img class="w-6 h-6" :src="url + category.category_image" alt="" />-->
                <h2 class="md:text-sm sm:text-xs xs:text-xxs text-center">
                  <strong>MORE</strong>
                </h2>
              </button>
            </li>
          </ul>
        </div>
        <div class="store">
          <!--<div class="flex justify-between w-full">
            <h2 class="capitalize text-sm">{{ category.category_name }}</h2>
            <div>
              <button
                class="text-brown hover:text-orange uppercase text-xxs p-2"
                @click="orderloadbatches('high')"
              >
                High to low <i class="fas fa-sort-amount-up-alt"></i>
              </button>
              <button
                class="text-brown hover:text-orange uppercase text-xxs mr-2"
                @click="orderloadbatches('low')"
              >
                Low to high <i class="fas fa-sort-amount-down-alt"></i>
              </button>
            </div>
          </div>-->
          <ul class="batchcontainer">
            <li v-for="(batch, index) in batches" :key="index + batch.id">
              <product :product="batch" />
            </li>
          </ul>
          <div v-if="laraveldata" class="flex justify-end px-5">
            <pagination
              :data="laraveldata"
              @laravelgetpagedata="getData"
            ></pagination>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="w-full py-8">
      <!--<product-show
        v-if="clickbatch"
        :batch="clickbatch"
        @closeloadedbatch="closeloadedbatch"
      />-->
    </div>
  </div>
</template>
<script>
const API_URL = 'api/'
export default {
  name: 'Store',
  props: {
    openbatch: { type: Object, default: null },
    opencategory: { type: Object, default: null },
  },
  data() {
    return {
      url: API_URL + 'storage/',
      category: {
        category_name: 'fruits',
      },
      categories: [
        {
          id: 1,
          category_image: 'https://picsum.photos/200/300',
          category_name: 'Fruits',
        },
        {
          id: 2,
          category_image: 'https://picsum.photos/200/300',
          category_name: 'trees',
        },
        {
          id: 3,
          category_image: 'https://picsum.photos/200/300',
          category_name: 'Minerals',
        },
        {
          id: 4,
          category_image: 'https://picsum.photos/200/300',
          category_name: 'Vegetables',
        },
      ],
      batches: [
        {
          name: 'Fish',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Copper',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Mangoes',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Apples',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Avacados',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Water melon',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Bananas',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Oranges',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Green Grams',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Pawpaws',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Sugarcane',
          img: 'https://picsum.photos/200/300',
        },
        {
          name: 'Pears',
          img: 'https://picsum.photos/200/300',
        },
      ],
      clickbatch: this.openbatch,
      laraveldata: null,
      category_page: null,
      category_last_page: null,
      category_previous_page: null,
    }
  },
  methods: {
    loadcategorybathes(index) {
      alert(index)
    },
  },
}
/*
import pagination from '../tiny_components/pagination.vue'
import { API_URL } from '../env.js'
import getHeader from '../config.js'
import AppStore from '../store/Appstore.js'

const appstore = AppStore
// let userstore = appstore.state.user;
const accountstore = appstore.state.account

const header = getHeader()

function comparetolow(a, b) {
  // Use toUpperCase() to ignore character casing
  const batchA = a.sale_price
  const batchB = b.sale_price

  let comparison = 0
  if (batchA > batchB) {
    comparison = 1
  } else if (batchA < batchB) {
    comparison = -1
  }
  return comparison
}
function comparetohigh(a, b) {
  // Use toUpperCase() to ignore character casing
  const batchA = a.sale_price
  const batchB = b.sale_price

  let comparison = 0
  if (batchA < batchB) {
    comparison = 1
  } else if (batchA > batchB) {
    comparison = -1
  }
  return comparison
}

export default {
  name: 'Store',
  components: {
    StoreSearch,
    ProductShow,
    pagination,
  },
  props: {
    openbatch: { type: Object, default: null },
    opencategory: { type: Object, default: null },
  },
  data() {
    return {
      url: API_URL + 'storage/',
      categories: null,
      batches: null,
      clickbatch: this.openbatch,
      laraveldata: null,
      category_page: null,
      category_last_page: null,
      category_previous_page: null,
    }
  },
  watch: {
    opencategory(val) {
      this.getPromo(val)
    },
  },
  mounted() {
    if (this.opencategory) {
      this.getPromo(this.opencategory)
    } else {
      this.loadBatches()
    }
    this.loadcategories()
  },
  methods: {
    getPromo(category) {
      this.$http
        .get(
          API_URL +
            `api/categories/` +
            accountstore.store +
            `/batches/` +
            category.id,
          { headers: header }
        )
        .then((response) => {
          this.getbatches(response)
        })
    },
    loadcategories() {
      this.$http
        .get(API_URL + 'api/categories', { headers: header })
        .then((response) => {
          this.category(response)
        })
    },
    category(data) {
      if (data.status === 200) {
        this.category_previous_page = this.category_page
        this.category_page = data.data.current_page
        this.categories = data.data.data
      }
    },
    previouscategory() {
      this.category_page = this.category_page - 1
      this.$http
        .get(API_URL + 'api/categories?page=' + this.category_page, {
          headers: header,
        })
        .then((response) => {
          this.category(response)
        })
    },
    morecategory() {
      if (this.category_page < this.category_last_page) {
        this.category_page = this.category_page + 1
        this.$http
          .get(API_URL + 'api/categories?page=' + this.category_page, {
            headers: header,
          })
          .then((response) => {
            this.category(response)
          })
      }
    },
    loadBatches() {
      const storeId = accountstore.store

      this.$http
        .get(API_URL + `api/batch/store/` + storeId, { headers: header })
        .then((response) => {
          this.getbatches(response)
        })
    },
    viewproduct(index) {
      this.$http
        .get(API_URL + `api/batch/` + this.batches[index].id, {
          headers: header,
        })
        .then((response) => {
          this.clickbatch = response.data
        })
        .catch(function (error) {
          const notify = {
            message: error.response.data,
            status: 'fail',
            code: error.response.status,
          }
          appstore.dispatch('account/setNotificationAsync', notify)
        })
    },
    closeloadedbatch() {
      this.clickbatch = null
    },
    loadcategorybathes(index) {
      const category = this.categories[index]

      this.$http
        .get(
          API_URL +
            `api/categories/` +
            accountstore.store +
            `/batches/` +
            category.id,
          { headers: header }
        )
        .then((response) => {
          this.getbatches(response)
        })
    },
    getbatches(data) {
      if (data.status === 200) {
        this.laraveldata = data.data
        this.batches = data.data.data
      }
    },
    getData(variable) {
      const urls = variable.url
      const page = variable.page

      this.$http
        .get(urls + '?page=' + page, { headers: header })
        .then((response) => {
          this.getbatches(response)
        })
    },
    addtocart(index) {
      // event.preventDefault();
      const batch = this.batches[index]
      appstore.dispatch('account/setAddtocart', batch)
    },
    orderloadbatches(order) {
      let batches
      if (order === 'high') {
        batches = this.batches.sort(comparetohigh)
      } else {
        batches = this.batches.sort(comparetolow)
      }

      this.batches = batches
    },
    searchedbatch(variable) {
      this.clickbatch = null
      this.clickbatch = variable
    },
  },
} */
</script>
