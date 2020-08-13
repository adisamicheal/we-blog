<template>
  <div id="app">
    <Navbar class="nav"/>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view/>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../src/components/Navbar";
import Footer from "../src/components/Footer";

export default {
  name: 'App',
  components: {
    Navbar,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
.font {
  font-family: 'Lato', sans-serif;
}
.spinner {
    display: block;
    margin-top: auto;
}
.pixel-spinner, .pixel-spinner * {
    box-sizing: border-box;
}

.pixel-spinner {
  height: 70px;
  width: 70px;
  margin: auto;
  display: block;
  margin-top: 50px;
  /* display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center; */
}

.pixel-spinner .pixel-spinner-inner {
  width: calc(70px / 7);
  height: calc(70px / 7);
  background-color: #041705;
  color: #041705;
  box-shadow: 15px 15px  0 0,
              -15px -15px  0 0,
              15px -15px  0 0,
             -15px 15px  0 0,
             0 15px  0 0,
             15px 0  0 0,
             -15px 0  0 0,
             0 -15px 0 0;
    animation: pixel-spinner-animation 2000ms linear infinite;
}

    @keyframes pixel-spinner-animation {
      50% {
        box-shadow: 20px 20px 0px 0px,
                    -20px -20px 0px 0px,
                    20px -20px 0px 0px,
                    -20px 20px 0px 0px,
                    0px 10px 0px 0px,
                    10px 0px 0px 0px,
                    -10px 0px 0px 0px,
                    0px -10px 0px 0px;
      }
      75% {
        box-shadow: 20px 20px 0px 0px,
                    -20px -20px 0px 0px,
                    20px -20px 0px 0px,
                    -20px 20px 0px 0px,
                    0px 10px 0px 0px,
                    10px 0px 0px 0px,
                    -10px 0px 0px 0px,
                    0px -10px 0px 0px;
      }
      100% {
        transform: rotate(360deg);
      }
    }
</style>
