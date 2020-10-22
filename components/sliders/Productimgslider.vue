<style scoped>
body {
  -webkit-font-smoothing: antialiased;
}

* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

/* End Non-Essential  */

.box {
  height: 100%;
  width: 100%;
  font-size: 12px;
}
.property-card {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  position: relative;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  height: 15em;
  overflow: hidden;
}
/* ^-- The margin bottom is necessary for the drop shadow otherwise it gets clipped in certain cases. */

/* Top Half of card, image. */

.property-image {
  padding: 1em 2em;
  position: Absolute;
  top: 0px;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  background-image: url('https://cdn.photographylife.com/wp-content/uploads/2017/01/What-is-landscape-photography.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  height: 100%;
  display: block;
  justify-content: center;
  width: 100%;
}

/* Bottom Card Section */

.property-description {
  color: white;
  height: 0em;
  width: 100%;
  position: absolute;
  bottom: 0em;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  padding: 0px 1em;
  text-align: center;
}

/* Social Icons */

.property-social-icons {
  position: absolute;
  bottom: 1em;

  height: auto;
  width: auto;
  left: 1em;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
}
.turnimg {
  height: 2em;
}

.turndes {
  height: 80%;
}

.property-image-title {
  text-align: center;
  position: absolute;
  width: 100%;
  display: flex;
  justify-content: center;
  margin: 0 auto;
  top: 0;
  opacity: 1;
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s;
  color: black;
  font-size: 1.2em;
}

.active {
  background-color: var(--primary-color);
  width: 0.41rem;
  height: 0.4rem;
  outline: none;
  border-radius: 20px;
}
button {
  outline: none;
  background-color: var(--logo-prominent-color);
}

button :hover {
  outline: none;
}
.price {
  font-size: 25px;
}
.imgageholder {
  height: 100%;
  display: block;
  justify-content: center;
  width: 100%;
  position: static;
}
.slider {
  height: 1500px;
  background-color: aqua;
}
.sliderbtn {
  width: 0.5rem;
  height: 0.5rem;
  border-radius: 20px;
}
.slidehandler {
  align-content: center;
  justify-content: center;
}
.fulldetails {
  font-size: 16px;
  font-family: var(--main-font);
  color: var(--logo-prominent-color);
}

.moreinfo {
  width: 50%;
  position: absolute;
  bottom: 0px;
  left: 20%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  transition: 0.4ms;
  transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
}
.rotatebtn {
  display: none;
}
.line {
  width: 100%;
  height: 0.8px;
  margin: 2.8px;
  background-color: white;
}
.infobtn {
  width: 100px;
  background-color: transparent;
}
@media (min-width: 600px) {
  .box {
    border-bottom: 0.1px solid rgba(216, 212, 216, 0.349);
    height: 100%;
    width: 100%;
    font-size: 12px;
    border-radius: 0px;
  }
  .property-card {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    position: relative;
    -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
    -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
    transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
    height: 16em;
    overflow: hidden;
  }
  .property-image {
    height: 100%;
    display: block;
    justify-content: center;
    width: 100%;
    border-radius: 0px;
  }
  .matatuimg {
    width: 100%;
    height: auto;
    margin: 0;
    padding: 0;
  }
  .slidehandler {
    width: 100%;
  }
  .fulldetails {
    padding: 4px;
    font-size: 15px;
  }
  .mataction {
    position: absolute;
    bottom: 0;
    background-color: transparent;
    right: 0;
    transition: 0.4ms;
    transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .mataction button {
    background-color: var(--primary-color);
    margin: 15px;
    padding: 10px;
    color: white;
    border-radius: 5px;
  }
  .movedmataction {
    transform: translateY(340px);
  }
  .movedcancelaction {
    transform: translateY(40px);
  }
  .turnimg {
    height: 2em;
  }

  .turndes {
    height: 14em;

    padding: 0.5em 1em;
  }
  .moreinfo {
    width: 50%;
    position: absolute;
    bottom: 0px;
    left: 20%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    transition: 0.4ms;
    transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .rotatebtn {
    display: none;
  }
  .line {
    width: 100%;
    height: 0.8px;
    margin: 2.5px;
    background-color: white;
  }
  .infobtn {
    width: 55px;
    background-color: transparent;
  }
  .price {
    font-size: 35px;
  }
}
</style>
<template>
  <div class="property-card box">
    <div
      class="property-image"
      :class="{ turnimg: details }"
      :style="{ backgroundImage: 'url(' + slide[slidenumber].img + ')' }"
    >
      <div class="property-image-title">
        <div class="slidehandler w-full flex justify-center">
          <ul class="flex flex-row">
            <li v-for="x in slide.length" :key="x" class="m-1">
              <button
                class="sliderbtn rounded-sm"
                :class="{ active: slidenumber == x - 1 }"
                @click="slidenumber = x - 1"
              ></button>
            </li>
          </ul>
        </div>

        <!-- Optional <h5>Card Title</h5> If you want it, turn on the CSS also. -->
      </div>
      <div class="moreinfo" :class="{ rotatebtn: details }">
        <button class="infobtn" @click="details = true">
          <div class="line"></div>
          <div class="line"></div>
          <div class="line"></div>
        </button>
      </div>
    </div>
    <div
      class="property-description"
      :class="{ turndes: details }"
      @click="details = false"
    >
      <div class="fulldetails">
        <p class="price">KSH{{ newfeed.price }}</p>
        <p class="text-left italic">category: {{ newfeed.category }}</p>
        <p class="text-left italic">farm: {{ newfeed.farm }}</p>
        <p class="text-left italic">amount: {{ newfeed.amount }}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    newfeed: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      details: false,
      isSet: false,
      slide: [
        {
          id: 1,
          name: 'Night rider',
          img: 'https://picsum.photos/240/350',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 2,
          name: 'Wolverine',
          img: 'https://picsum.photos/230/340',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'fiohgiodfhgdfiohdofighio0i rjio m',
          name: 'King kong',
          img: 'https://picsum.photos/220/330',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'asfusdfhsdjfhsdofreioafjxdion',
          name: 'Cybrgo',
          img: 'https://picsum.photos/210/310',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'iosefupifusdpisd',
          name: 'Spiderman',
          img: 'https://picsum.photos/200/300',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'sdofusdifusdoif',
          name: 'Avengers',
          img: 'https://picsum.photos/190/290',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
        {
          id: 'sdfjlkfhf',
          name: 'Kingdom come',
          img: 'https://picsum.photos/200/250',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
        {
          id: 'dfgnklklgdf',
          name: 'German Shepherd',
          img: 'https://picsum.photos/200/300',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
        {
          id: 'dfhhfklsd',
          name: 'German Shepherd',
          img: 'https://picsum.photos/190/300',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
        {
          id: 'efjhsjklf',
          name: 'German Shepherd',
          img: 'https://picsum.photos/180/300',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
        {
          id: '4rjer',
          name: 'German Shepherd',
          img: 'https://picsum.photos/170/300',
          board_time: '18:00pm',
          music: 'Hiphop',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
        },
      ],
      slidenumber: 0,
    }
  },
  method: {
    countDownTimer() {
      if (this.slidenumber <= this.slide.length) {
        this.countDownTimer()
        setTimeout(() => {
          this.slidenumber += 1
          this.countDownTimer()
        }, 1000)
      } else {
        this.slidenumber = 0
      }
    },
  },
  created() {
    // this.countDownTimer
  },
}
</script>
