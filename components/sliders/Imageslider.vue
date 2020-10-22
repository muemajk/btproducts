<style scoped>
.active {
  background-color: var(--primary-color);
  width: 0.41rem;
  height: 0.4rem;
  outline: none;
  border-radius: 20px;
}
button {
  outline: none;
  background-color: rgb(245, 243, 246);
}

button :hover {
  outline: none;
}

.box {
  display: flex;
  flex-direction: column;
  border-bottom: 0.1px solid rgba(216, 212, 216, 0.349);
  height: 250px;
  width: 100%;
  font-size: 12px;
  position: absolute;
  top: 0;
}
.imageholder {
  height: auto;
  display: block;
  justify-content: center;
  width: 100%;
  position: static;
}
.matatuimg {
  width: 100%;
  height: 250px;
  margin: 0;
  padding: 0;
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
  position: absolute;
  align-content: center;
  justify-content: center;
  margin: 0 auto;
  bottom: 0;
}
.moreinfo {
  width: 50%;
  position: absolute;
  background-color: rgba(44, 44, 44, 0.162);
  display: none;
  bottom: 20px;
  left: 2px;
  height: 80px;
  color: white;
  flex-direction: column;
  justify-content: flex-start;
  text-align: left;
  transition: 0.4ms;
  animation: fadeinout 1.2s linear forwards;
  transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
}
.box:hover .moreinfo {
  display: flex;
}
.moreinfo h1 {
  font-size: 20px;
  font-family: var(--main-font);
  font-weight: bold;
  text-shadow: 2px 2px #908e8e68;
}
.moreinfo P {
  text-align: left;
  width: auto;
  font-size: 15px;
  font-style: italic;
}
@media (min-width: 600px) {
  .box {
    display: flex;
    flex-direction: column;
    border-bottom: 0.1px solid rgba(216, 212, 216, 0.349);
    height: fit-content;
    width: 100%;
    font-size: 12px;
    position: absolute;
    top: 0;
  }
  .imageholder {
    height: auto;
    display: block;
    justify-content: center;
    width: 100%;
  }
  .matatuimg {
    width: 100%;
    height: 350px;
    margin: 0;
    padding: 0;
  }
  .moreinfo {
    width: 50%;
    position: absolute;
    background-color: rgba(44, 44, 44, 0.162);
    display: none;
    bottom: 20px;
    left: 2px;
    height: 120px;
    color: white;
    flex-direction: column;
    justify-content: flex-start;
    text-align: left;
    transition: 0.4ms;
    animation: fadeinout 1.2s linear forwards;
    transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .moreinfo h1 {
    font-size: 30px;
    font-family: var(--main-font);
    font-weight: bold;
  }
  .moreinfo P {
    text-align: left;
    width: auto;
    font-size: 20px;
    font-style: italic;
  }
  @keyframes fadeinout {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 0.5;
    }
    100% {
      opacity: 1;
    }
  }
}
@media (min-width: 1033px) {
  .box {
    display: flex;
    flex-direction: column;
    border-bottom: 0.1px solid rgba(216, 212, 216, 0.349);
    height: fit-content;
    width: 100%;
    font-size: 12px;
  }
  .imageholder {
    height: auto;
    display: block;
    justify-content: center;
    width: 100%;
  }
  .matatuimg {
    width: 100%;
    height: 350px;
    margin: 0;
    padding: 0;
  }
  .moreinfo {
    width: 50%;
    position: absolute;
    background-color: rgba(44, 44, 44, 0.162);
    display: none;
    bottom: 20px;
    left: 2px;
    height: 120px;
    color: white;
    flex-direction: column;
    justify-content: flex-start;
    text-align: left;
    transition: 0.4ms;
    animation: fadeinout 1.2s linear forwards;
    transition-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .moreinfo h1 {
    font-size: 40px;
    font-family: var(--main-font);
    font-weight: bold;
  }
  .moreinfo P {
    text-align: left;
    width: auto;
    font-size: 20px;
    font-style: italic;
  }
  @keyframes fadeinout {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 0.5;
    }
    100% {
      opacity: 1;
    }
  }
}
</style>
<template>
  <div class="box">
    <div class="imageholder">
      <img
        class="h-auto matatuimg"
        :src="slide[slidenumber].img"
        width="100%"
        height="auto"
      />
    </div>
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
    <div class="moreinfo">
      <h1>{{ slide[slidenumber].title }}</h1>
      <p>{{ slide[slidenumber].category }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      slide: [
        {
          id: 1,
          title: 'Pineapple farm in Mombasa, Kenya.',
          img: 'https://picsum.photos/700/450',
          board_time: '18:00pm',
          category: 'Agriculture',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 2,
          title: 'Watermelon farm in Makueni, Kenya.',
          img: 'https://picsum.photos/700/460',
          board_time: '18:00pm',
          category: 'Agriculture',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'fiohgiodfhgdfiohdofighio0i rjio m',
          title: 'Fish farm in Kisumu, Kenya.',
          img: 'https://picsum.photos/700/470',
          board_time: '18:00pm',
          category: 'Agriculture',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'asfusdfhsdjfhsdofreioafjxdion',
          title: 'Dairy farm in limuru, Kenya.',
          img: 'https://picsum.photos/710/480',
          board_time: '18:00pm',
          category: 'Agriculture',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
        },
        {
          id: 'iosefupifusdpisd',
          title: 'Copper mine in Congo.',
          img: 'https://picsum.photos/720/480',
          board_time: '18:00pm',
          category: 'Agriculture',
          driver: 'Johnthan Muthama',
          conductor: 'Peter Ochieng',
          stage: 'kitengela',
          type: 'Nganya',
          verified: true,
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
