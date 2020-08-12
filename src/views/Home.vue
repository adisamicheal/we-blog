<template>
  <div class="home font">
    <!-- <div class="typewriter">
      <div class="typewriter-text">Welcome to my blog.</div>
    </div> -->
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div class="hero">
      <div class="text">
        <div class="typewriter">
          <div class="typewriter-text">Welcome to my blog.</div>
       </div>
      </div>
      <div>
        <img src="../assets/blog.jpg" alt="">
      </div>
    </div>

    <div class="section-2">
      <div class="text-container">
        <p class="deep-blue">01</p>
        <h4 class="small-heading">Lifestyle</h4>
        <p class="body-text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
          sed do eiusmod tempor incididunt ut labore et dolore magna 
          aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
          ullamco laboris nisi ut aliquip ex ea commodo consequat. 
          Duis aute irure dolor in reprehenderit.
        </p>
      </div>
      <div>
        <img src="../assets/screen.svg" alt="analysis" />
      </div>
    </div>
    <div class="section-2 reverse light-blue-bg">
      <div>
        <img src="../assets/connect.svg" alt="graph" />
      </div>
      <div class="text-container">
        <p class="deep-blue">02</p>
        <h4 class="small-heading">Research</h4>
        <p class="body-text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
          sed do eiusmod tempor incididunt ut labore et dolore magna 
          aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
          ullamco laboris nisi ut aliquip ex ea commodo consequat. 
          Duis aute irure dolor in reprehenderit.
        </p>
      </div>
    </div>
    <div class="section-2">
      <div class="text-container">
        <p class="deep-blue">03</p>
        <h4 class="small-heading">Gists</h4>
        <p class="body-text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
          sed do eiusmod tempor incididunt ut labore et dolore magna 
          aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
          ullamco laboris nisi ut aliquip ex ea commodo consequat. 
          Duis aute irure dolor in reprehenderit.
        </p>
      </div>
      <div>
        <img src="../assets/screen.svg" alt="analysis" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  }
}
</script>

<style soped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.hero {
  display: flex;
  justify-content: space-between;
  padding: 0 100px;
}
.hero img {
  height: 500px;
}
.text {
  align-self: center;
}
.typewriter {
  font-family: Courier, monospace;
	display: inline-block;
}

.typewriter-text {
  display: inline-block;
	overflow: hidden;
  letter-spacing: 2px;
  animation: typing 5s steps(30, end), blink .75s step-end infinite;
  white-space: nowrap;
  font-size: 50px;
  font-weight: 700;
  border-right: 4px solid #ffcc00;
  box-sizing: border-box;
}
.section-2 {
  display: flex;
  justify-content: space-between;
  padding: 50px 100px;
  align-items: center;
}
.text-container {
  max-width: 489px;
}
.deep-blue {
  font-weight: 600;
  font-size: 24px;
  color: #041705;
  margin-bottom: 20px;
}
.body-text {
  font-size: 16px;
  line-height: 25px;
}
@keyframes typing {
    from { 
        width: 0% 
    }
    to { 
        width: 100% 
    }
}

@keyframes blink {
    from, to { 
        border-color: transparent 
    }
    50% { 
        border-color: #ffcc00;
    }
}

@media screen and (max-width: 768px) {
  .section-2 {
    padding: 20px;
    flex-direction: column;
  }
}
</style>