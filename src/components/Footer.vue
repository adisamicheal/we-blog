<template>
  <footer id="footer" class="bg font" >
    <div class="sec1">
      <div class="links">
        <ul>
          <li><router-link to="/blogs">Blogs</router-link></li>
          <li><router-link to="/about">About </router-link></li>
        </ul>
      </div>
      <hr />
      <div class="address">
        <ul>
          <li class="copyrigth">made with 
            <svg width="19" height="17" viewBox="0 0 19 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M18.23 5.02918C18.23 2.25161 15.9784 0 13.2013 0C11.5154 0 10.0278 0.83225 9.115 
                2.10432C8.20223 0.83225 6.71457 0 5.02918 0C2.25161 0 0 2.2511 0 5.02918C0 5.42262 0.0499452 
                5.80384 0.135566 6.17129C0.833779 10.5099 5.65757 15.087 9.115 16.3438C12.5719 15.087 17.3962 
                10.5099 18.0934 6.1718C18.1801 5.80435 18.23 5.42313 18.23 5.02918Z" fill="#78B159">
                </path>
            </svg> 
            <span> by <a href="https://twitter.com/michellead" target="blank"> Micheal Adisa</a></span></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<script>

export default {
};
</script>

<style scoped>
#footer {
  display: flex;
  padding: 0 50px;
}
.bg {
    background: #041705;
}
.sec1 {
  width: 100%;
}
.links,
.address {
  max-width: 35%;
  display: block;
  margin: auto;
  padding: 20px 0;
}
.links ul,
.address ul {
  list-style: none;
  display: flex;
  justify-content: space-around;
  margin: 16px 0;
}
.address a {
  text-decoration: none;
  color: #ffffff;
}
.links ul > li,
.links ul > li > a {
  font-style: normal;
  font-weight: 900;
  font-size: 14px;
  line-height: 16px;
  letter-spacing: -0.4px;
  color: #ffffff;
}
.links ul > li > a:hover {
  color: #f9bc0a;
}
.links ul > li > .router-link-exact-active {
  color: #f9bc0a;
}
hr {
  width: 95%;
  background-color: #ffffff;
  height: 1px;
  border: none;
}
.address ul > li > span {
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 14px;
  letter-spacing: -0.4px;
  color: #ffffff;
}
.address > ul > li {
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 14px;
  letter-spacing: -0.4px;
  color: #ffffff;
}
.copyright {
    display: flex;
    align-items: center;
}
svg {
    margin-left: 10px;
    margin-right: 10px;
}
@media screen and (max-width: 768px) {
  .links,
  .address {
    max-width: none;
  }
  .address ul {
    display: block;
    text-align: center;
    margin: 0;
  }
  .address ul > li {
    margin-bottom: 10px;
  }
}
</style>
