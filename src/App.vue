<template>
  <div id="app">
    <header class="main-header">
      <div class="tools-nav bg-secondary py-1">
        <div class="container">
          <div class="d-flex justify-content-end align-items-center">
            <a href="https://line.me/ti/p/Z_V4wL67B9" class="mx-1" target="_blank">
              <i class="fab fa-line"></i>
            </a>
            <a href="https://www.instagram.com/pin_jui_huang/" class="mx-1" target="_blank">
              <i class="fab fa-instagram"></i>
            </a>
            <a
              href="https://www.facebook.com/%E9%BB%83%E5%93%81%E7%9D%BF-Pin-Jui-104903445063158"
              class="mx-1"
              target="_blank"
            >
              <i class="fab fa-facebook-square"></i
            ></a>
          </div>
        </div>
      </div>
      <div class="container pt-4">
        <div class="row mx-0 w-100">
          <div class="col-4 pl-0">
            <div class="d-flex align-items-center h-100">
              <!--  -->
              <div
                class="mobile-menu-mask position-fixed"
                :class="{ active: menuState }"
                @click="menuState = false"
              ></div>
              <div
                class="mobile-menu-wrap d-block d-md-block position-fixed pt-5"
                :class="{ active: menuState }"
              >
                <button
                  type="button"
                  style="top:15px;right:15px;font-weight:900"
                  class="close position-absolute text-decoration-none"
                  @click.prevent="menuState = false"
                >
                  ×
                </button>
                <ul class="list-unstyled ">
                  <!-- <li style="border-bottom:1px solid #ced4da">
                    <router-link
                      to="/about"
                      class="h4 d-block py-3 pl-3 mb-0 text-decoration-none"
                      @click.native="menuState = false"
                      >ABOUT</router-link
                    >
                  </li> -->
                  <li style="border-bottom:1px solid #ced4da">
                    <router-link
                      to="/shop"
                      class="h4 d-block py-3 pl-3 mb-0 text-decoration-none"
                      @click.native="menuState = false"
                      >SHOP</router-link
                    >
                  </li>
                  <li style="border-bottom:1px solid #ced4da">
                    <router-link
                      to="/location"
                      class="h4 d-block py-3 pl-3 mb-0 text-decoration-none"
                      @click.native="menuState = false"
                      >LOCATION</router-link
                    >
                  </li>
                </ul>
              </div>

              <!--  -->
              <div class="menu-trigger d-md-none">
                <a href="#" @click.prevent="menuState = !menuState">
                  <b-icon
                    icon="grid-fill"
                    variant="primary"
                    class="header-icon"
                    style="width:25px;height:25px"
                  ></b-icon>
                </a>
              </div>
              <!--  -->
              <div class="menu-wrap">
                <ul class="list-unstyled d-none d-md-flex align-items-center mb-0">
                  <!-- <li>
                    <router-link to="/about">ABOUT</router-link>
                  </li>
                  <li class="mx-3">|</li> -->
                  <li><router-link to="/shop">SHOP</router-link></li>
                  <li class="mx-3">|</li>
                  <li><router-link to="/location">LOCATION</router-link></li>
                </ul>
              </div>
            </div>
          </div>

          <!--  -->
          <div class="col-4">
            <div class="d-flex justify-content-center align-items-center h-100">
              <!-- <router-link to="/" class="d-inline-block"> -->
                <img alt="Vue logo" src="./assets/logo.png" class="img-fluid" width="50px" />
              <!-- </router-link> -->
            </div>
          </div>
          <!--  -->
          <div class="col-4 pr-0">
            <div class="d-flex justify-content-end align-items-center h-100">
              <router-link to="/cart">
                <b-icon
                  icon="handbag-fill"
                  variant="primary"
                  class="header-icon"
                  style="width:25px;height:25px"
                ></b-icon>
              </router-link>
              <router-link to="/member">
                <b-icon
                  icon="person-fill"
                  variant="primary"
                  class="header-icon"
                  style="width:25px;height:25px;margin-left:16px"
                ></b-icon>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </header>
    <!--  -->
    <router-view />
    <!--  -->
    <footer class="main-footer bg-primary pt-4">
      <div class="fb-customerchat" page_id="104903445063158" minimized="false"></div>
      <div class="container">
        <div
          class="d-flex flex-column flex-lg-row justify-content-center align-items-center mb-lg-5"
        >
          <div
            class="fb-page mb-4 mb-lg-0 mx-lg-5"
            data-href="https://www.facebook.com/%E9%BB%83%E5%93%81%E7%9D%BF-Pin-Jui-104903445063158"
            data-width="380"
            data-hide-cover="false"
            data-show-facepile="false"
          ></div>
          <div class="mb-4 mb-lg-0 mx-lg-5">
            <h4>消費者服務</h4>
            <p class="mb-0">客服時間：週一至週五 10:00 - 18:00</p>
            <p class="mb-0">客服電話：0976-904-299</p>
            <p class="mb-0">客服信箱：fee8ack21@gmail.com</p>
          </div>
        </div>
      </div>
       <div style="background-color:#5b5b5b" class="py-2">
          <p class="mb-0 text-center" style="color:#ffffff80;font-size:14px">
            Copyright © 2020 Vue Shop. All rights reserved.
          </p>
        </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      menuState: false,
    };
  },
  methods: {},
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.main-header {
  .tools-nav a{
    color: #ffffffcc;
    &:hover{
      color: #ffffff;
    }
  }
  padding: {
    // top: 30px;
  }
  a {
    font-weight: bold;
  .header-icon{
    color: #ffffffcc;
  }
&:hover,
    &:hover .header-icon {
    color: black;
    }
    &.router-link-exact-active,
    &.router-link-exact-active:hover {
      // color: #42b983;
      text-decoration: none;
      pointer-events: none;
    }
    .header-icon:active {
      transform: scale(0.97);
    }
  }
  .mobile-menu-mask {
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
    background-color: #00000000;
    z-index: -100;
    transition: 0.15s;
    &.active {
      background-color: rgba(0, 0, 0, 0.6);
      z-index: 100;
    }
  }

  .mobile-menu-wrap {
    background-color: white;
    width: 300px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    margin-left: -500px;
    transition: 0.15s;
    z-index: 9999;
    &.active {
      margin-left: 0px;
    }
    li {
      a:hover {
        background-color: rgba(0, 0, 0, 0.2);
      }
    }
  }
}

.main-footer {
  p ,h4{
    color: #ffffffcc;
  }
}
</style>
