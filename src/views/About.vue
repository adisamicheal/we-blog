<template>
  <div class="about font">
    <h1>This is an about page</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
      sed do eiusmod tempor incididunt ut labore et dolore magna 
      aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
      ullamco laboris nisi ut aliquip ex ea commodo consequat. 
      Duis aute irure dolor in reprehenderit in voluptate velit 
      esse cillum dolore eu fugiat nulla pariatur. Excepteur sint 
      occaecat cupidatat non proident, sunt in culpa qui officia 
      deserunt mollit anim id est laborum.
    </p>
  </div>

</template>
<style scoped>
    .about {
      padding: 30px 100px;
      height: 100vh;
    }
    p {
      line-height: 25px;
      margin-top: 50px;
    }
@media screen and (max-width: 768px) {
  .about {
    padding: 20px;
  }
}
</style>
