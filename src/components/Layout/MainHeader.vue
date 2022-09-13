<template>
  <header :class="{'extended-top-banner': isHeaderHeightDoubleLineForTopBanner}">
    <top-banner></top-banner>
    <div class="main-header">
      <div class="main-header__left">
        <router-link to="/" class="logo-block">
          <img :src="images.PetifyLogo" alt="petify logo" />
        </router-link>
        <!-- <ul class="nav-left">
          <li>
            <router-link to="/products">Products</router-link>
          </li>
        </ul> -->
      </div>

      <nav class="main-header__right">

      </nav>
    </div>
  </header>
</template>

<script>
import { mapGetters } from 'vuex'

import TopBanner from '@Component/Layout/TopBanner.vue'

import PetifyLogo from '@Asset/images/printr-logo.jpg'

export default {
  name: 'MainHeader',
  components: {
    TopBanner
  },
  data() {
    return {
      images: {
        PetifyLogo,
        CartIcon,
      },
      isMobile: true,
      isDesktop: false,
      isHeaderHeightDoubleLineForTopBanner: false
    }
  },
  watch:{
    $route (to, from){
      this.setHeaderHeight()
    }
  },
  mounted() {
    this.setDeviceVariables()
    this.setHeaderHeight()
    window.addEventListener('resize', () => {
      this.setDeviceVariables()
      this.setHeaderHeight()
    }, false)
  },
  methods: {
    setDeviceVariables() {
      if (document.documentElement.clientWidth < 1024) {
        this.isMobile = true
        this.isDesktop = false
      } else {
        this.isMobile = false
        this.isDesktop = true
      }
    },
    setHeaderHeight() {
      if (this.isMobile) {
        switch (this.$route.path) {
          case '/':
          case '/faq':
          case '/refunds':
          case '/terms':
          case '/privacy-policy':
            this.isHeaderHeightDoubleLineForTopBanner = true
            break;
          default:
            this.isHeaderHeightDoubleLineForTopBanner = false
          }
      }
    },
    openLoginPopup() {
      this.$store.commit('toggleLoginModal', {
        loginModalTriggeredFrom: 'MainHeader',
      })
    },
    toggleMenu() {
      this.$store.commit('toggleMenuModal')
    },
  },
}
</script>

<style lang="scss" scoped>
@import '../../scss/partials/variables';
$background-color: $dark-color;

header {
  position: fixed;
  // top: 25px;
  top: 0;
  left: 0;
  right: 0;
  height: 90px;
  min-height: 65px;
  transition: transform 0.5s, opacity 0.5s;
  transition: top 0.3s ease 0s; /* only transition top property */
  z-index: 10;
  background: #ffffff;
  box-shadow: 0 4px 4px -2px #ff0000;

  @media only screen and (min-width: 1024px) {
    height: 95px;
  }

  &.extended-top-banner {
    height: 95px;
  }
}

.main-header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  background: $brand-color-3;
  height: 65px;
  width: 100%;
  color: $accent-color;
  margin: 0 auto;

  @media only screen and (min-width: 1024px) {
    justify-content: initial;
    height: 70px;
    padding: 0 0 0 16px;
  }
}

.main-header__left {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  font-size: 18px;
  font-weight: 800;
  padding-left: 16px;
  @media only screen and (min-width: 1024px) {
    padding: 0;
  }

  .logo-block {
    display: flex;
    align-items: center;
  }

  img {
    max-height: 65px;
    width: 100%;
    @media only screen and (min-width: 1024px) {
      max-height: 70px;
    }
  }
}

.nav-left {
  color: #ffffff;
  display: flex;
  padding: 10px 0 0 0;
  margin: 0 0 0 30px;
  li {
    a {
      display: block;
      padding: 10px 5px;
    }
  }
}

.main-header__right {
  flex: 1;
  display: flex;
  justify-content: flex-end;
  align-self: center;

  .btn-cta--header {
    display: none;
    height: 48px;
    align-self: center;
    margin-right: 14px;
    @media only screen and (min-width: 1024px) {
      display: inline-block;
    }
  }

  .hi-user {
    display: none;
    margin-right: 15px;
    @media only screen and (min-width: 1024px) {
      display: flex;
      align-items: center;
    }
  }

  .cart-icon-container {
    display: flex;
    height: 32px;
    align-self: center;
    max-height: 32px;
    min-height: 0;
    min-width: 32px;
    color: #6fd862;
    overflow: hidden;
    padding: 5px 10px;
    border-radius: 16px;
    border: 1px solid #6fd862;
    margin-right: 15px;
    @media only screen and (max-width: 700px) {
      margin-right: 1px;  
    }
    img {
      width: 20px;
      height: 20px;
    }
    span {
      display: block;
      margin-left: 5px;
      align-self: center;
    }
  }
}

.hamburger--mobile {
  // flex: 1;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.hamburger--mobile__container {
  display: flex;
  height: 65px;
  width: 65px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.alignment {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 24px;
  width: 30px;

  div {
    height: 3px;
    width: 100%;
    background-color: $accent-color;
  }
}
</style>
