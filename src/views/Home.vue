<template>
  <main class="page-content">
    <!-- <header-banner id="3" :styleClass="['black-friday-sale']"></header-banner> -->
    <section class="hero">
      <div class="left">
        <img class="logo" :src="images.LogoTogether" alt="logo together">
        <div class="scroll">
          <div class="scroll-box">
            <div class="text">scroll down</div>
          </div>
        </div>
      </div>
      <!-- <div class="mobile-supported">
        <div class="mobile-supported-text">
          Supported by:
        </div>
        <div class="mobile-supported-logos">
          <img :src="images.AvbobLogo" alt="av logo">
          <img :src="images.PetifyLogo" alt="petify logo">
          <img :src="images.WizardzLogo" alt="wiz logo">
        </div>
      </div> -->
      <div class="right">

        <div class="hero__content">
          <div class="h1-text">
            <span class="welcome">WELCOME TO</span>
            <h1><span class="red">Printr</span>, <span class="blue">your</span> <br/><span class="red">business</span> to <span class="blue">business</span> <br/>printing solution</h1>
          </div>
        </div>

        <div class="contact-text">Contact us for access to our online ordering platform,<br/>where quality meets efficiency.<br/>from order to delivery.</div>
        <ul class="contact-details">
          <li><img :src="images.LocationImage" alt="location icon"> <span>South Africa</span></li>
          <!-- <li><img :src="images.MobileImage" alt="mobile icon"> <span>076 521 3844</span></li>
          <li><img :src="images.EmailImage" alt="mobile icon"> <span>christian@printr.co.za</span></li> -->
        </ul>

        <div class="business-card-container">
          <div class="business-card">
            <div class="head">
              <div class="head-left">
                <div class="head-left__top">CHRISTIAN SCOTT</div>
                <div class="head-left__bottom">Printr (Pty) Ltd</div>
              </div>
              <div class="head-right">
                <div class="img-block">
                  <img :src="images.TinyP" alt="small P">
                </div>
              </div>
            </div>
            <div class="body">
              <div class="body-left">
                <div class="detail">
                  <div class="title">PHONE</div>
                  <div class="title-desc">076 521 3844</div>
                </div>
                <div class="detail">
                  <div class="title">EMAIL</div>
                  <div class="title-desc">christian@printr.co.za</div>
                </div>
                <div class="detail">
                  <div class="title">WEB</div>
                  <div class="title-desc">www.printr.co.za</div>
                </div>
              </div>
              <div class="body-right">
                <img :src="images.QRCodeImage" alt="qrcode">
              </div>
            </div>
          </div>
        </div>

        <!-- <div class="desktop-supported">
          <div class="desktop-supported-text">
            Supported by:
          </div>
          <div class="desktop-supported-logos">
            <img :src="images.AvbobLogo" alt="av logo">
            <img :src="images.PetifyLogo" alt="petify logo">
            <img :src="images.WizardzLogo" alt="wiz logo">
          </div>
        </div> -->
      </div>
    </section>
  </main>
</template>

<script>
import HeaderBanner from '@Component/Layout/HeaderBanner.vue'

import LogoTogether from '@Asset/images/logo-together.png'
import LocationImage from '@Asset/images/icons/location-icon.png'
import MobileImage from '@Asset/images/icons/mobile-icon.png'
import QRCodeImage from '@Asset/images/qrcode.svg'
import TinyP from '@Asset/images/p-logo-tiny.png'

import AvbobLogo from '@Asset/images/avbob-logo.png'
import WizardzLogo from '@Asset/images/wizardz-logo.png'
import PetifyLogo from '@Asset/images/petify-logo.png'

export default {
  name: 'Home',
  metaInfo: {
    title: 'Printr · Your Business to Business Printing Solution',
    meta: [{
      vmid: '1',
      name: 'description',
      content: 'Printr is disrupting printing for business in South Africa. Be it for interior decor or resell purposes. We do the design, manufacturing, and delivery.'
    },
    {
      vmid: 'og:site_name',
      property: 'og:site_name',
      content: 'Petify',
    },
    {
      property: 'og:title',
      content: 'Petify - Original Pet Art Company',
      vmid: 'og:title'
    },
    {
      vmid: 'og:description',
      property: 'og:description',
      content: 'Petify &#183; Gift your loved ones a giggle. We explore new innovative personalized pet products that makes you feel good. We deliver all over South Africa.'
    },
    {
      vmid: 'og:image',
      property: 'og:image',
      content: 'https://firebasestorage.googleapis.com/v0/b/petify-aa5b2.appspot.com/o/socials%2FFB-share.png?alt=media&token=74e846e0-3953-4202-a77f-49c507d72ca1',
    },
    {
      vmid: 'og:image:width',
      property: 'og:image:width',
      content: '680',
    },
    {
      vmid: 'og:image:height',
      property: 'og:image:height',
      content: '354',
    },
    {
      vmid: 'og:image:alt',
      property: 'og:image:alt',
      content: 'Petify Pet Art Company',
    }],
  },
  components: {
    HeaderBanner,
  },
  data() {
    return {
      images: {
        LogoTogether,
        AvbobLogo,
        WizardzLogo,
        PetifyLogo,
        LocationImage,
        MobileImage,
        QRCodeImage,
        TinyP,
      }
    }
  },
}
</script>
<style lang="scss" scoped>
@import '../scss/partials/variables';

.page-content {
  & > div {
    overflow: hidden;
  }
}

.hero {
  position: relative;
  display: flex;
  flex-direction: row-reverse;
  height: 100%;
  color: #4a5568;
  // padding: 40px 0 30px 0;
}

.right {
  position: relative;
  flex: 3;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 10px;
}

.left {
  position: relative;
  flex: 4;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  background: $brand-color-3;

  // @media only screen and (max-width: 900px) {
  //   display: none;
  // }

  .logo {
    height: 280px;
  }

  .scroll {
    display: none;
    position: absolute;
    bottom: 60px;
    left: 0;
    right: 0;
  }

  $bounce-height: 25px;

  .scroll-box {
    height: $bounce-height;	
    // overflow: hidden;
    position: relative;
    color: #ffffff;
  }
  .text {
    color: #ffffff;
    position: absolute;
    width: 100%;
    height: 100%;
    margin: 0;
    line-height: $bounce-height;
    text-align: center;
    /* Starting position */
    -moz-transform:translateY(50%);
    -webkit-transform:translateY(50%);	
    transform:translateY(50%);
    /* Apply animation to this element */	
    -moz-animation: vertically 2s linear infinite alternate;
    -webkit-animation: vertically 2s linear infinite alternate;
    animation: vertically 2s linear infinite alternate;
  }
    /* Move it (define the animation) */
  @-moz-keyframes vertically {
    0%   { -moz-transform: translateY(50%); }
    100% { -moz-transform: translateY(-50%); }
  }
  @-webkit-keyframes vertically {
    0%   { -webkit-transform: translateY(50%); }
    100% { -webkit-transform: translateY(-50%); }
  }
  @keyframes vertically {
    0%   { 
      -moz-transform: translateY(50%); /* Browser bug fix */
      -webkit-transform: translateY(50%); /* Browser bug fix */
      transform: translateY(50%); 		
    }
    100% { 
      -moz-transform: translateY(-50%); /* Browser bug fix */
      -webkit-transform: translateY(-50%); /* Browser bug fix */
      transform: translateY(-50%); 
    }
  }

}

.hero__content {
  display: flex;
  flex-direction: row;
  flex-grow: 0;
  justify-content: center;

  .welcome {
    font-size: 20px;
    font-weight: 500;
  }

  h1 {
    font-size: 46px;
    font-weight: 500;
    line-height: 1;
  }
}

.h1-text {
  .welcome {
    display: inline-block;
    padding-bottom: 10px;
  }
  h1 {
    line-height: 1.1;
    .red {
      color: $accent-color;
    }
    .blue {
      color: $brand-color-2;
    }
  }
}

.contact-text {
  width: 100%;
  max-width: 447px;
  padding-top: 10px;
  margin: 0 auto;
}

.contact-details {
  list-style: none;
  width: 100%;
  max-width: 447px;
  padding-top: 10px;
  margin: 0 auto;

  li {
    img {
      height: 14px;
    }
  }
}

.business-card-container {
  width: 100%;
  max-width: 447px;
  padding-top: 10px;
  margin: 0 auto;
}

.business-card {
  width: 100%;
  max-width: 355px;
  background: $brand-color-3;
  padding: 20px;

  .head {
    display: flex;
    justify-content: space-between;
    padding-bottom: 5px;
    border-bottom: 1px solid $accent-color;

    .head-left {
      &__top {
        color: #ffffff;
      }
      &__bottom {
        font-size: 13px;
        color: grey;
      }
    }
    .head-right {

      .img-block {
        width: 40px;
        text-align: center;
        img {
          width: 20px;
        }
      }
    }
  }
  .body {
    display: flex;
    justify-content: space-between;
    font-size: 13px;
    padding-top: 5px;

    .body-left {
      .detail {
        .title {
          font-size: 12px;
          color: #ffffff;
        }
        .title-desc {
          color: grey;
        }
      }
    }

    .body-right {
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      img {
        width: 40px;
      }
    }
  }
}

.desktop-supported {
  display: flex;
  flex-direction: column;
  width: 100%;
  max-width: 447px;
  padding: 20px 10px 0 10px;
  margin: 0 auto;
}
.desktop-supported-logos {
  display: flex;
  justify-content: space-around;
  padding-top: 5px;
  img {
    height: 40px;
  }
}

.mobile-supported {
  display: none;
  flex-direction: column;
  width: 100%;
  max-width: 447px;
  padding: 30px 10px;
  margin: 0 auto;
}

.mobile-supported-text {
  text-align: center;
  font-size: 30px;
}


.mobile-supported-logos {
  display: flex;
  flex-direction: column;
  padding-top: 5px;
  align-items: center;

  img {
    // max-height: 40px;
    width: 250px;
    max-height: initial;
    height: 100%;
    margin-top: 15px;
  }
}

@media only screen and (max-width: 1100px) {
  .right, .left {
    flex: 1 !important;
  }
}

@media only screen and (max-width: 900px) {
  .hero {
    display: initial;
  }

  .right, .left {
    height: 100vh;
  }

  .scroll {
    display: block !important;
  }

  .desktop-supported {
    display: none !important;
  }

  .mobile-supported {
    display: flex;
  }

  .contact-text {
    padding-top: 40px;
  }

  .contact-details {
    padding-top: 20px;
  }
}

@media only screen and (max-width: 500px) {

  .hero__content {
    justify-content: flex-start;
  }

  h1 {
    font-size: 30px !important;
  }
}

</style>
