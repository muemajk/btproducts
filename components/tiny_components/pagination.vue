<template>
  <ul class="flex bg-gray-400 py-2 px-2 rounded divide-x">
    <li v-if="diplayreverselist" class="px-2">
      <button
        class="text-base text-white hover:text-green3"
        @click="reverselistpages()"
      >
        BACK
      </button>
    </li>
    <li v-for="n in diplayedinlistpages" :key="n" class="px-2">
      <button
        class="text-base text-white hover:text-green3"
        @click="loadpagedata(n)"
      >
        {{ n }}
      </button>
    </li>
    <li v-if="diplayaddlist" class="px-2">
      <button
        class="text-base text-white hover:text-green3"
        @click="listpages()"
      >
        ...
      </button>
    </li>
    <li v-if="diplayaddlist" class="px-2">
      <button
        class="text-base text-white hover:text-green3"
        @click="loadpagedata(last_page)"
      >
        {{ last_page }}
      </button>
    </li>
  </ul>
</template>
<script>
export default {
  name: 'Pagination',
  props: {
    data: { type: Object, default: null },
  },
  data() {
    return {
      first_page: null,
      current_page: null,
      last_page: null,
      clicked_page: null,
      counts: 10,
      displaypages: null,
      diplayedinlistpages: [],
      diplayaddlist: false,
      url: null,
      diplayreverselist: false,
    }
  },
  mounted() {
    if (this.data) {
      this.first_page = this.data.from
      this.current_page = this.data.current_page
      this.url = this.data.path
      this.last_page = this.data.last_page
    }
    this.initatelist()
  },
  methods: {
    initatelist() {
      let intiator = 1
      if (this.first_page < this.last_page) {
        let count = this.first_page
        do {
          if (intiator < this.last_page) {
            this.diplayedinlistpages.push(count)
            if (intiator < this.counts) {
              intiator++
            } else {
              this.diplayaddlist = true
            }
          } else {
            this.diplayedinlistpages.push(count)
          }
          count++
        } while (this.diplayedinlistpages.length < intiator)
      } else {
        this.diplayedinlistpages.push(this.first_page)
      }
    },
    loadpagedata(page) {
      const obj = {
        url: this.url,
        page,
      }
      this.$emit('laravelgetpagedata', obj)
    },
    listpages() {
      const displaypages = this.diplayedinlistpages[
        this.diplayedinlistpages.length - 1
      ]

      this.diplayedinlistpages = []
      let i
      let num = displaypages
      for (i = 0; i < this.counts; i++) {
        num = num + 1
        if (num < this.last_page) {
          this.diplayedinlistpages.push(num)
          this.diplayreverselist = true
        } else if (num === this.last_page) {
          this.diplayedinlistpages.push(num)
          this.diplayaddlist = false
        } else {
          this.diplayaddlist = false
        }
      }
    },
    reverselistpages() {
      const displaypages = this.diplayedinlistpages[
        this.diplayedinlistpages.length - 1
      ]

      this.diplayedinlistpages = []
      let i
      let num = displaypages
      for (i = 0; i < this.counts; i++) {
        num = num - 1
        if (num > this.first_page) {
          this.diplayedinlistpages.push(num)
        } else if (num === this.first_page) {
          this.diplayedinlistpages.push(num)
          this.diplayaddlist = true
          this.diplayreverselist = false
        } else {
          this.diplayaddlist = true
          this.diplayreverselist = false
        }
      }
      this.diplayedinlistpages = this.diplayedinlistpages.sort((a, b) => a - b)
    },
  },
}
</script>
