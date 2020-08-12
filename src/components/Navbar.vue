<template>
  <div class="Navbar font">
      <div>
          <router-link to="/"><img src="../assets/wejapa.png" alt="logo" class="logo"></router-link>
      </div>
      <div class="links">
          <ul>
             <li>
                <router-link to="/">Home</router-link>
            </li>
            <li>
                <router-link to="/blogs">Blog</router-link>
            </li>
            <li>
                <router-link to="/about">About</router-link>
             </li>
          </ul>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.Navbar {
    padding: 20px 100px;
    background: #041705;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.logo {
    width: 50px;
    height: 50px;
}
.links ul{
    list-style: none;
    display: flex;
}
.links a {
    color: aliceblue;
    font-size: 18px;
    text-decoration: none;
    margin-left: 20px;
}
</style>