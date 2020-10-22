<template>
  <div class="container">
    <div class="slidersection">
      <Imageslider />
    </div>
    <div class="infomation">
      <div style="height: 50px">
        <h1>OUR COMPANY</h1>
      </div>
      <div class="infosection">
        <div class="info">
          <div>
            <p>
              Bt products are mined with the lastest grade industrial machines
              to extract minerals effectively. Our proud investors have provided
              resources necessary for the progresses we have made.
            </p>
          </div>
        </div>
        <div class="infoimg">
          <div>
            <video class="coalvideo" width="auto" height="auto" controls>
              <source src="../assets/content/coal.mp4" type="video/mp4" />
              Your browser does not support the video tag.
            </video>
          </div>
        </div>
      </div>
    </div>
    <div class="storesection">
      <h1>Special offers</h1>
      <p>
        With our large array of products, we as btproducts are committed to
        friendly prices and special offers,
      </p>
      <ministore />
      <button class="morebtn">MORE</button>
    </div>
    <div class="aboutsection">
      <h1>About Us</h1>
      <div class="aboutus">
        <div class="aboutUsimg">
          <img
            width="320px"
            height="350px"
            alt="No image"
            src="../assets/img/aboutcharacter.svg"
          />
        </div>
        <div class="about">
          <div>
            <p>
              We are a team of hardworking individuals that have a vision of
              providing high value mineral products to clients existing all over
              the world.
            </p>
          </div>
        </div>
      </div>
      <div class="aboutus">
        <div class="about">
          <div>
            <p>
              We are a team of hardworking individuals that have a vision of
              providing high value mineral products to clients existing all over
              the world.
            </p>
          </div>
          <div class="aboutUsimg">
            <img
              width="320px"
              height="350px"
              alt="No image"
              src="../assets/img/aboutfemale.svg"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="blogsection">
      <h1>Blogs</h1>
      <p>
        We are committed to having a positive impact on the society and the
        environment. See how we are addressing our role to communities through
        blogging and other intuitives
      </p>
      <div class="blog">
        <blogstore />
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
::-webkit-scrollbar {
  width: 20px;
  display: none;
}
.container {
  margin: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  width: 100%;
  position: relative;
  background-color: white;
  padding: 0;
}
h1 {
  font-family: var(--sub-title-font);
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
.slidersection {
  height: auto;
  min-height: 300px;
  width: 100%;
  position: relative;
  top: 0;
}
.storesection {
  width: auto;
  height: auto;
  min-height: 400px;
  margin: 10px;
  margin-top: 10px;
}
.storesection p {
  font-family: var(--main-font);
  font-style: italic;
}
.infosection {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(auto-fit, minmax(5em, 1fr));
  height: auto;
  grid-template-areas:
    'info'
    'infoimg';
  margin: -25px 0 0 -25px;
}
.infomation {
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  text-align: center;
  height: auto;
  position: relative;
}
.info {
  grid-area: info;
  width: auto;
  height: 100px;
  color: #000;
}
.infoimg {
  grid-area: infoimg;
  width: auto;
  height: auto;
  display: flex;
  justify-content: center;
}
.coalvideo {
  width: auto;
  height: 250px;
  border-radius: 10px;
  outline: none;
}
.info div > p {
  font-family: var(--main-font);
  font-style: italic;
  font-size: 20px;
}
.morebtn {
  width: 100%;
  border: 1px solid rgb(240, 238, 238);
  border-bottom: 1px solid rgb(86, 84, 84);
  height: 40px;
  font-size: 25px;
  font-family: var(--main-font);
  color: rgb(63, 63, 63);
}
.aboutus {
  display: grid;
  grid-template-areas:
    'aboutUsimg'
    'about';
}
.aboutUsimg {
  grid-area: aboutUsimg;
}
.about {
  text-align: center;
  display: flex;
  justify-content: center;
  grid-area: about;
}
.about div {
  margin: auto auto;
  width: 50%;
  font-family: var(--main-font);
  font-style: italic;
}
@media (min-width: 600px) {
  .container {
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    width: 100%;
    background-color: white;
    padding: 0;
    position: relative;
  }
  .slidersection {
    height: auto;
    min-height: 400px;
  }
  .infosection {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(10em, 1fr));
    grid-template-rows: repeat(auto-fit, minmax(10em, 1fr));
    height: 350px;
    grid-gap: 3rem;
    grid-template-areas: 'info infoimg';
    margin: -25px 0 0 -25px;
  }
  .info {
    grid-area: info;
    width: auto;
    height: auto;
    text-align: center;
    justify-content: center;
  }
  .info div {
    text-align: center;
    justify-content: center;
    margin: auto;
    margin-top: 15%;
    margin-bottom: 15%;
    width: 60%;
    padding: 10px;
  }
  .info div > p {
    font-family: var(--main-font);
    font-style: italic;
  }
  .infoimg {
    grid-area: infoimg;
    width: auto;
    height: auto;
    padding: 25px 0 0 25px;
  }
  .infoimg div {
    margin: -25px 0 0 -25px;
  }
  .coalvideo {
    width: auto;
    height: 300px;
  }
  .morebtn {
    width: 300px;
    border: 1px solid rgb(86, 84, 84);
    height: 40px;
    font-size: 25px;
    font-family: var(--main-font);
    color: rgb(63, 63, 63);
  }
  .morebtn:hover {
    background-color: var(--primary-color);
    border: none;
    color: white;
  }
  .aboutsection {
    margin: 0 auto;
    width: auto;
    height: auto;
  }
  .aboutus {
    display: flex;
    flex-direction: row;
  }

  .about {
    text-align: center;
    display: flex;
    justify-content: center;
  }
  .about div {
    margin: auto auto;
    width: 50%;
    font-family: var(--main-font);
    font-style: italic;
  }
  .blogsection {
    height: auto;
    min-height: 300px;
  }
  .blogsection h1,
  p {
    text-align: center;
  }
  .blogsection p {
    font-family: var(--main-font);
    font-style: italic;
  }
}
</style>
