n
<style scoped>
.emptynotification {
  display: none;
  height: 50px;
}
.failnotification {
  box-sizing: border-box;
  background-color: rgb(247, 51, 51);
  height: 30px;
  z-index: 2;
  width: auto;
}

.successnotification {
  box-sizing: border-box;
  @apply bg-green2;
  z-index: 2;
  height: 30px;
  width: auto;
}
.messagearea {
  background-color: rgba(252, 252, 252, 0.11);
  width: auto;
  float: left;
  font-size: 12px;
  height: 100%;
  padding: 5px;
  padding-top: 7px;
}
.actionarea {
  background-color: rgba(3, 3, 3, 0.37);
  width: 20px;
  float: left;
  padding: 5px;
  height: 100%;
}
</style>
<template>
  <div
    v-if="message && show == true"
    class="fixed bottom-0"
    :class="responsetype"
  >
    <div class="messagearea">
      <p>{{ message.message }}</p>
    </div>
    <div class="actionarea">
      <button @click="closenotification">
        <span class="text-white"><i class="fas fa-times"></i></span>
      </button>
    </div>
  </div>
</template>
<script>
// const accountstore = Appstore.state.account

export default {
  name: 'Notification',
  props: {
    response: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      message: null,
      status: null,
      code: null,
      show: true,
      count: 25,
    }
  },
  computed: {
    Responsetrack() {
      return null // Appstore.getters['account/get_notification']
    },
    responsetype() {
      if (this.message.status === 'success') {
        return {
          successnotification: true && this.show === true,
        }
      } else if (this.message.status === 'fail') {
        return {
          failnotification: true && this.show === true,
        }
      } else {
        return {
          emptynotification: this.show === true,
        }
      }
    },
  },
  watch: {
    Responsetrack(newResponse) {
      if (newResponse) {
        this.message = newResponse
        this.show = true
        this.countdownTimer()
      }
    },
    count(newValue) {
      if (newValue <= 0) {
        this.show = false
      }
    },
  },
  mounted() {
    this.getResponse()
  },
  created() {
    this.countdownTimer()
  },
  methods: {
    getResponse() {
      this.show = true
      this.message = this.response
      this.countdownTimer()
    },
    getStoreNotification() {
      this.show = true
      const notification = null // accountstore.notify
      this.message = notification
      this.countdownTimer()
    },
    countdownTimer() {
      const count = this.count
      if (this.show === true) {
        if (count > 0) {
          setTimeout(() => {
            this.count--
            this.countdownTimer()
          }, 1000)
        }
      }
    },
    closenotification() {
      this.show = false
      this.message = null
    },
  },
}
</script>
