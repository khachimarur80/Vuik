<template>
  <div class="hero">
    <img height="100%" width="100%" class="banner" :src="hero.src" :alt="hero.alt"/>
    <div class="contents">
      <div class="logo">
        <img :alt="logo.alt" :src="logo.src" height="100%" width="100%"/>
      </div>
      <div class="slogan">
        {{ slogan }}
      </div>
      <div class="text">
        {{ text }}
      </div>
      <br>
      <div class="action">
        <button class="left">
          Get free estimate
        </button>
        <button class="right">
          <img src="@/assets/icons/play-circle-outline.svg" class="inline-img"/>
          See our work
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    logo: {
      src: require('@/assets/logo.png'),
      lazySrc: require('@/assets/logo.png'),
      alt: '',
    },
    hero: {
      src: require('@/assets/images/hero/hero.webp'),
      lazySrc: require('@/assets/lazy-images/hero/hero.webp'),
      alt: '',
    },
    slogan: "Oak Harbor's Top Rated Painting Contractors",
    text: "Here at 2-A-T Painting, we take pride in our top-notch services and top-tier quality craftsmanship. Our experienced painters are professional, knowledgeable, and dedicated to providing the best customer service and workmanship in the industry.",
  })
}
</script>

<style scoped>
  .hero {
    min-height: calc(100vh - 100px);
    width: 100%;
    background: red;
    display: flex;
    justify-content: center;
    align-items: center;
    padding-top: 100px;
    position: relative;
    overflow: hidden;
  }
  .banner {
    position: absolute;
    top: -0px;
    right: -0px;
    left: -0px;
    bottom: -0px;
    z-index: 0;
    filter: brightness(.5);
  }
  .contents {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 70%;
    max-width: 700px;
    z-index: 3;
    color: var(--vk-text-light);
  }

  .slogan {
    font-size: 50px;
    font-family: var(--vk-title-font);
    margin-top: 20px;
    margin-bottom: 50px;
  }
  .text {
    font-size: 25px;
    max-width: 800px;
    font-family: var(--vk-text-font);
  }
  .action {
    margin: 30px;
    display: flex;
    gap: 10px;
    justify-content: center;
  }
  .left, .right {
    border: none;
    height: 60px;
    width: 190px;
    text-transform: uppercase;
    border-radius: 10px;
    font-size: 16px;
    color: var(--vk-text-light);
    font-family: var(--vk-title-font);
    cursor: pointer;
    border: 2px solid transparent;
  }
  .left {
    background: var(--vk-primary);
    transition: border .3s ease-out, background .25s ease-out, color .15s ease-out;
  }
  .left:hover {
    background: transparent;
    border: 2px solid var(--vk-primary);
    color: var(--vk-primary);
  }
  .right {
    background: transparent;
    border: 2px solid var(--vk-text-light);
    transition: border .3s ease-out, background .25s ease-out, color .15s ease-out;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
  }
  .right:hover {
    color: var(--vk-primary);
    border-color: transparent;
    background: var(--vk-text-light);
  }
  .right:hover .inline-img {
    filter: invert(44%) sepia(80%) saturate(937%) hue-rotate(180deg) brightness(96%) contrast(98%);
  }
  .inline-img {
    filter: invert(100%);
    height: 30px;
    width: 30px;
  }
  .logo {
    height: 250px;
    width: 250px;
  }
  @media (max-width: 492px) {
    .hero {
      padding-top: 160px;
    }
    .logo {
      height: 120px;
      width: 120px;
    }
    .slogan {
      font-size: 30px;
    }
    .contents {
      width: calc(100% - 100px);
    }
    .text {
      font-size: 18px;
      line-height: 17px;
    }
    .action {
      flex-direction: column;
      gap: 20px;
    }
  }

  @media (min-width: 493px) and (max-width: 700px) {
    .hero {
      padding-top: 180px;
    }
    .logo {
      height: 180px;
      width: 180px;
    }
    .slogan {
      font-size: 36px;
    }
    .text {
      font-size: 22px;
      line-height: 21px;
    }
    .contents {
      width: 80%;
    }
  }
</style>
