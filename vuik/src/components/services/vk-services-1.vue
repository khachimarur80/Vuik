<template>
  <div class="services">
    <div class="section-name">
      Services
    </div>
    <div class="section-header">
      {{ slogan }}
    </div>
    <div class="section-description">
      {{ text }}
    </div>
    <div class="contents">
      <div class="service" v-for="(service, i) in services" :key="i">
        <div class="service-image">
          <img :src="service.image.src" :alt="service.image.alt" height="100%"/>
        </div>
        <div class="service-details">
          <div class="service-icon">
            <img :src="service.icon.src" :alt="service.icon.alt" height="60%" width="60%"/>
          </div>
          <div class="service-name">
            {{ service.name }}
          </div>
          <div class="service-text">
            {{ service.text }}
          </div>
          <div class="service-actions">
            <button class="seemore">
              See more
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    services: [
      {
        image: {
          src: require("@/assets/images/services/research.webp"),
          alt: "Map research image",
        },
        icon: {
          src: require("@/assets/icons/map-search-outline.svg"),
          alt: "Map search icon",
        },
        name: "Route research",
        text: "Regular cleaning of your solar panels will improve the life and efficiency of your panels"
      },
      {
        image: {
          src: require("@/assets/images/services/rental.webp"),
          alt: "Car in row with mountain background",
        },
        icon: {
          src: require("@/assets/icons/car-key.svg"),
          alt: "Car key icon",
        },
        name: "Car rental",
        text: "Our PVC coated galvanized steel wire mesh will protect your panels from pigeons and other critters"
      },
      {
        image: {
          src: require("@/assets/images/services/repair.webp"),
          alt: "Man repairing a car",
        },
        icon: {
          src: require("@/assets/icons/car-wrench.svg"),
          alt: "Car repair icon",
        },
        name: "Car repair",
        text: "We have the proper training and equipment to properly clean and maintain your Tesla Solar Roof"
      },
      {
        image: {
          src: require("@/assets/images/services/cleaning.webp"),
          alt: "Image of car wheel being cleaned",
        },
        icon: {
          src: require("@/assets/icons/vacuum.svg"),
          alt: "Vacuum icon"
        },
        name: "Car cleaning",
        text: "Experience the joy of having all of your windows professionally hand cleaned"
      }
    ],
    slogan: "Protect your Investment in Solar Panels",
    text: "Dirt, dust, and debris accumulation on solar panels can significantly reduce their energy output and lead to costly repairs.",
  })
}
</script>

<style scoped>
  .section-name {
    margin-bottom: 10px;
    font-weight: bold;
    font-family: var(--vk-title-font);
    color: var(--vk-primary);
    font-size: 22px;
  }
  .section-header {
    font-size: 40px;
    width: 50%;
    font-weight: bold;
    font-family: var(--vk-title-font);
  }
  .section-description {
    font-size: 20px;
    width: 60%;
    margin-top: 30px;
    margin-bottom: 50px;
    font-family: var(--vk-text-font);
    max-width: 800px;
  }
  .services {
    width: 100%;
    height: fit-content;
    padding: 50px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
  .contents {
    width: calc(100%);
    display: flex;
    justify-content: space-evenly;
    max-width: 1400px;
  }
  .service {
    width: calc(25% - 50px);
    max-width: 300px;
    overflow: hidden;
    display: flex;
    align-items: center;
    flex-direction: column;
    position: relative;
  }
  .service-image {
    width: 100%;
    aspect-ratio: 2/3;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    border-radius: 10px;
    overflow: hidden;
  }
  .service-image img {
    flex-shrink: 0;
    min-width: 100%;
    min-height: 100%;
    object-fit: cover;
    transition: transform .25s ease-out, filter .25s ease-out;
  }
  .service-image:hover img {
    filter: blur(3px) brightness(.8);
    transform: scale(1.2);
  }
  .service-details {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    border: 1px solid var(--vk-text-light);
    box-shadow: 0px 0px 2px 0px var(--vk-text);
    border-radius: 10px;
    position: relative;
    background: var(--vk-background);
    width: calc(100% - 30px);
    padding-top: 70px;
    height: fit-content;
    transform: translateY(-33%);
  }
  .service-icon {
    height: 100px;
    width: 100px;
    position: absolute;
    top: -50px;
    box-sizing: border-box;
    border: 4px solid var(--vk-primary);
    border-radius: 50%;
    background: var(--vk-background);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .service-icon img {
    filter: invert(44%) sepia(80%) saturate(937%) hue-rotate(180deg) brightness(96%) contrast(98%);
  }
  .service-name {
    font-weight: bold;
    font-family: var(--vk-title-font);
    font-size: 22px;
  }
  .service-text {
    margin-top: 20px;
    font-size: 18px;
    font-family: var(--vk-text-font);
    margin-bottom: 20px;
    width: 85%;
  }
  .seemore {
    border: 2px solid transparent;
    border-radius: 5px;
    width: 115px;
    height: 35px;
    font-size: 16px;
    text-transform: uppercase;
    margin-bottom: 15px;
    color: var(--vk-primary);
    font-weight: bold;
    transition: border .3s ease-out;
    background: none;
    cursor: pointer;
  }
  .seemore:hover {
    border: 2px solid var(--vk-primary);
  }
  @media (max-width: 600px) {
    .service {
      width: calc(100% - 40px);
      max-width: 1000px;
      margin-bottom: -30px;
    }
    .service-image {
      aspect-ratio: 3/2;
    }
    .service-icon {
      height: 80px;
      width: 80px;
      top: -40px;
    }
    .service-details {
      padding-top: 50px;
    }
    .contents {
      flex-wrap: wrap;
    }
    .services {
      padding-left: 10px;
      padding-right: 10px;
    }
    .section-description {
      font-size: 16px;
      width: 75%;
    }
    .section-header {
      font-size: 22px;
      width: 90%;
    }
    .section-name {
      font-size: 18px;
    }
  }
  @media (min-width: 601px) and (max-width: 800px) {
    .service {
      width: calc(100% - 40px);
      max-width: 1000px;
      margin-bottom: -30px;
    }
    .service-image {
      aspect-ratio: 4/2;
    }
    .contents {
      flex-wrap: wrap;
    }
    .section-description {
      font-size: 18px;
      width: 75%;
    }
    .section-header {
      font-size: 30px;
      width: 90%;
    }
    .section-name {
      font-size: 22px;
    }
  }
  @media (min-width: 801px) and (max-width: 1200px) {
    .service {
      width: calc(50% - 50px);
      max-width: 400px;
      margin-bottom: -30px;
    }
    .service-image {
      aspect-ratio: 2/2;
    }
    .services {
      padding-left: 20px;
      padding-right: 20px;
    }
    .contents {
      flex-wrap: wrap;
    }
    .section-description {
      font-size: 20px;
      width: 60%;
    }
    .section-header {
      font-size: 35px;
      width: 70%;
    }
    .section-name {
      font-size: 24px;
    }
  }
</style>
