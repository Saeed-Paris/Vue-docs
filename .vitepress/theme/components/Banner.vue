<script setup>
import { ref } from 'vue'

/**
 * Adding a new banner:
 * 1. uncomment the banner slot in ../index.ts
 * 2. uncomment and update BANNER_ID in ../../inlined-scripts/restorePreferences.ts
 * 3. update --vt-banner-height if necessary
 */

let open = $ref(true)

const banner = ref({
  assets: "LEVELUP2022",
  cta: "GET OFFER",
  link: "/sales/levelup2022",
  static: "LEVELUP2022",
  subtitle: "Access 800+ lessons including the Vue.js 3 Masterclass",
  title: "Less than <strong>48 hours</strong> to get 45% off at Vue School"
})

/**
 * Call this if the banner is dismissible
 */
function dismiss() {
  open = false
  document.documentElement.classList.add('banner-dismissed')
  localStorage.setItem(`vue-docs-banner-${window.__VUE_BANNER_ID__}`, 'true')
}
</script>

<template>
  <div class="banner" v-if="open">
    <a
      id="vs-top"
      :href="`https://vueschool.io${banner.link}?friend=vuejs&utm_source=vuejs&utm_medium=website&utm_campaign=affiliate&utm_content=top_banner`"
      target="_blank"
      :class="banner.assets">
      <div class="vs-background-wrapper">
        <div class="vs-logo" />
        <div class="vs-core">
          <div class="vs-slogan-wrapper">
            <div class="vs-slogan" v-html="banner.title" />
            <div class="vs-subline" v-html="banner.subtitle" />
          </div>
          <div class="vs-button-wrapper">
            <div class="vs-button">
              {{ banner.cta }}
            </div>
          </div>
        </div>
        <div
          class="vs-close"
          @click.prevent.stop="dismiss">
          <img src="https://vueschool.io/images/close.svg" alt="Close">
        </div>
      </div>
    </a>
  </div>
</template>

<style>
html:not(.banner-dismissed) {
  --vt-banner-height: 72px;
}

#vs-top {
  display: block;
  box-sizing: border-box;
  height: 72px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  line-height: 1;
}

#vs-top .vs-background-wrapper {
  align-items: center;
  justify-content: center;
  display: flex;
  padding: 0 10px;
  height: 100%;
  width: 100%;
}

#vs-top:hover {
  text-decoration: none;
}

#vs-top:hover .vs-core .vs-button {
  background-image: linear-gradient(to bottom, #5ccc45, #419E2D), linear-gradient(to bottom, #388f26, #50b83b);
}

#vs-top .vs-logo {
  position: absolute;
  left: 10px;
  width: 36px;
  height: 42px;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
}

#vs-top .vs-core {
  display: flex;
  align-items: center;
  width: 288px;
}

#vs-top .vs-core .vs-slogan-wrapper {
  text-align: center;
  width: 184px;
  margin: 0 auto;
}

#vs-top .vs-core .vs-slogan {
  font-weight: bold;
  font-size: 12px;
  font-family: 'Roboto', Arial, sans-serif;
}

#vs-top .vs-core .vs-subline {
  font-size: 10px;
  font-family: 'Roboto', Arial, sans-serif;
  text-align: center;
}

#vs-top .vs-core .vs-button-wrapper {
  padding: 2px;
  background-image: linear-gradient(to bottom, #388f26, #50b83b);
  border-radius: 60px;
  overflow: hidden;
}

#vs-top .vs-core .vs-button {
  background-image: linear-gradient(to bottom, #5ccc45, #368c24), linear-gradient(to bottom, #388f26, #50b83b);
  border-radius: 60px;
  color: #FFF;
  padding: 8px 6px;
  font-weight: bold;
  text-transform: uppercase;
  text-align: center;
  font-size: 10px;
  letter-spacing: 0.3px;
  white-space: nowrap;
}

#vs-top .vs-close {
  right: 0;
  position: absolute;
  padding: 10px;
}

#vs-top .vs-close:hover {
  color: #56d8ff;
}

@media (min-width: 680px) {
  #vs-top .vs-core {
    width: auto;
  }

  #vs-top .vs-core .vs-slogan-wrapper {
    margin: 0 12px 0 0;
    width: 458px;
  }

  #vs-top .vs-core .vs-slogan {
    font-size: 17px;
  }

  #vs-top .vs-core .vs-subline {
    font-size: 12px;
    margin-top: 4px;
  }

  #vs-top .vs-core .vs-button {
    font-size: 13px;
    padding: 8px 15px;
  }
}

@media (min-width: 1280px) {
  #vs-top .vs-logo {
    left: 20px;
    width: 104px;
  }

  #vs-top .vs-core {
    margin-right: 0;
  }

  #vs-top .vs-core .vs-slogan-wrapper {
    width: auto;
  }

  #vs-top .vs-core .vs-subline {
    font-size: 15px;
  }
}

/* LEVELUP2022
******************************************/

#vs-top.LEVELUP2022 {
  color: #121733;
  background: #EEF5FF;
}

#vs-top.LEVELUP2022 .vs-logo {
  background-image: url(https://vueschool.io/images/mark-vueschool.svg);
}

#vs-top.LEVELUP2022 .vs-core .vs-slogan {
  color: #121733;
}

#vs-top.LEVELUP2022 .vs-core .vs-slogan strong {
  color: #ff2556;
}

#vs-top.LEVELUP2022 .vs-core .vs-subline {
  color: #394170;
}

#vs-top.LEVELUP2022 .vs-core .vs-subline strong {
  color: #48aa34;
}

#vs-top.LEVELUP2022 .vs-background-wrapper {
  background-image: url(https://vueschool.io/images/banners/assets/LEVELUP2022/bg-mobile.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top right;
}

#vs-top.LEVELUP2022 .vs-core .vs-button-wrapper {
  background-image: linear-gradient(to bottom, #d71b46, #fd2455);
}

#vs-top.LEVELUP2022 .vs-core .vs-button {
  background-image: linear-gradient(to bottom, #ff2556, #d51b44), linear-gradient(to bottom, #d71b46, #fd2455);
}

@media (min-width: 680px) {
  #vs-top.LEVELUP2022 .vs-background-wrapper {
    background-image: url(https://vueschool.io/images/banners/assets/LEVELUP2022/bg-tablet.png);
  }
}

@media (min-width: 1280px) {
  #vs-top.LEVELUP2022 .vs-logo {
    background-image: url(https://vueschool.io/images/icons/logo.svg);
  }

  #vs-top.LEVELUP2022 .vs-background-wrapper {
    background-image:
      url(https://vueschool.io/images/banners/assets/LEVELUP2022/bg-desktop-left.png),
      url(https://vueschool.io/images/banners/assets/LEVELUP2022/bg-desktop-right.png);
    background-position:
      top left -120px,
      top right -120px;
    background-size: contain;
    background-repeat: no-repeat;
  }
}

@media (min-width: 1536px) {
  #vs-top.LEVELUP2022 .vs-background-wrapper {
    background-position:
      top left,
      top right;
  }
}
</style>

<style scoped>
.banner {
  position: fixed;
  z-index: var(--vp-z-index-banner);
  box-sizing: border-box;
  top: 0;
  left: 0;
  right: 0;
  height: var(--vt-banner-height);
  line-height: 0;
  text-align: center;
  font-size: 12px;
  font-weight: 600;
  color: #fff;
  background-color: var(--vt-c-green);
}

.banner-dismissed .banner {
  display: none;
}
</style>
