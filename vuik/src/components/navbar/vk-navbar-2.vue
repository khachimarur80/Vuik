<template>
  <div class="navbar">
    <div class="navbar-header">
      <div class="navbar-logo">
        <img :alt="logo.alt" :src="logo.src" height="100%"/>
      </div>
      <div class="navbar-title">
        Aurie
      </div>
    </div>
    <div class="navbar-items">
      <a class="navbar-item" v-for="(item, i) in items" :href="item.href" :key="i">
        {{ item.name }}
      </a>
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
    items: [
      { name: 'Item 1', href: '/#'},
      { name: 'Item 2', href: '/#'},
      { name: 'Item 3', href: '/#'},
      { name: 'Item 4', href: '/#'},
      { name: 'Item 5', href: '/#'},
    ]
  })
}
</script>

<style scoped>
  .navbar {
    height: 100px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
    overflow: hidden;
    position: absolute;
    background: transparent;
  }
  .navbar-header {
    width: fit-content;
    height: 100% ;
    box-sizing: border-box;
    padding: 10px;
    display: flex;
    gap: 20px;
  }
  .navbar-logo {
    height: 100%;
    box-sizing: border-box;
    padding: 5px;
    aspect-ratio: 1;
  }
  .navbar-title {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 10px;
    font-size: 35px;
    color: var(--vk-text);
    font-family: var(--vk-title-font);
  }
  .navbar-items {
    flex: 1;
    justify-content: flex-end; 
    display: flex;
    padding-right: 30px;
    padding-left: 30px;
    gap: 15px;
    box-sizing: border-box;
    min-width: fit-content;
  }
  .navbar-item {
    text-decoration: none;
    min-width: fit-content;
    color: var(--vk-text);
    font-size: 18px;
    padding: 3px 8px 3px 8px;
    position: relative;
    z-index: 2;
  }
  .navbar-item:before {
    transition: background .15s ease-out;
    content: '';
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    position: absolute;
    background-color: transparent;
    filter: opacity(.3);
    border-radius: 6px;
    z-index: -1;
  }
  .navbar-item:hover:before {
    background: var(--vk-background-light);
  }

  @media (max-width: 492px) {
    .navbar-header {
      height: 120px;
    }
    .navbar {
      height: fit-content;
      padding-bottom: 10px;
      gap: 0px;
    }
    .navbar-items {
      justify-content: center;
      gap: 0px;
    }
  }

  @media (min-width: 493px) and (max-width: 690px) {
    .navbar-header {
      height: 130px;
    }
    .navbar {
      height: fit-content;
      padding-bottom: 10px;
      gap: 0px;
    }
    .navbar-items {
      justify-content: center;
    }
  }
</style>
