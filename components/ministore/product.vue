<style scoped>
/* Optional

.property-image-title
{
text-align:center;
position:Relative;
top:30%;
opacity:0;
transition:all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s;
color:black;
font-size:1.2em;
}

.property-card:hover .property-image-title
{
opacity:1;
}
*/
@keyframes loadpage {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
h5 {
  margin: 0px;
  font-size: 1em;
  font-weight: 700;
  text-transform: uppercase;
}

p {
  font-size: 12px;
}
button {
  font-size: 0.7em;
  color: #fafafc;
  outline: none;
  font-family: var(--main-font);
  font-weight: 400;
}

.property-card {
  animation: 1s ease-out 0s 1 loadpage;
  font-family: var(--main-font);
  box-shadow: none;
  height: 16.4em;
  width: 10em;
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
  overflow: hidden;
}
.property-image {
  width: 10em;
  height: 100%;
  position: Absolute;
  top: 0px;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  background-size: cover;
  background-repeat: no-repeat;
}
.cart {
  width: 100%;
  background-color: var(--primary-color);
}
.property-description {
  width: 10em;
  height: auto;
  background-color: #fafafc;
  position: absolute;
  bottom: 0em;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  -o-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  padding: 0.1em 0.2em;
  text-align: justify;
}
.property-description p {
  text-align: left;
}
@media (min-width: 600px) {
  h5 {
    margin: 0px;
    font-size: 0.8em;
    font-weight: 700;
    text-transform: uppercase;
  }

  p {
    font-size: 12px;
  }
  button {
    font-size: 0.7em;
    color: #fafafc;
    outline: none;
  }

  /* End Non-Essential  */

  .property-card {
    animation: 1s ease-out 0s 1 loadpage;
    height: 17.2em;
    width: 12em;
    border-radius: 0;
    border: 0.5px solid rgba(154, 152, 152, 0.514);
    -webkit-box-shadow: 3px 3px 5px 6px rgba(216, 214, 214, 0.349); /* Safari 3-4, iOS 4.0.2 - 4.2, Android 2.3+ */
    -moz-box-shadow: 3px 3px 5px 6px rgba(216, 214, 214, 0.349); /* Firefox 3.5 - 3.6 */
    box-shadow: 3px 3px 5px 6px rgba(216, 214, 214, 0.349);
  }
  /* ^-- The margin bottom is necessary for the drop shadow otherwise it gets clipped in certain cases. */

  /* Top Half of card, image. */

  .property-image {
    height: 100%;
    width: 12em;
  }

  /* Bottom Card Section */

  .property-description {
    width: 12em;
    height: auto;
  }
  .property-description p {
    text-align: left;
  }
  .cart {
    border-radius: none;
  }
}
</style>
<template>
  <div class="property-card lg:w-24 m-auto">
    <div class="property-image">
      <Productimgslider :newfeed="details" />
    </div>
    <div class="property-description">
      <h5>{{ product.name }}</h5>
      <p>Stock: {{ details.amount }}</p>
      <p>Price: {{ details.price }}</p>
      <button class="cart w-full rounded-lg p-1 flex flex-row justify-center">
        ADD
      </button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      details: {
        price: 18.5,
        category: 'Fruits',
        farm: 'Machakos',
        amount: 18,
      },
    }
  },
}
</script>
