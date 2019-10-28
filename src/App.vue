<template>
  <div id="app" class="antialiased text-gray-900 _flex p-4 flex content-center justify-center">
    <div class="bg-gray-200 sm:px-2 lg:px-2 pt-2 pb-4 mx-auto w-full md:w-1/2">
      <carrousel-component :images="data"></carrousel-component>
    </div>
  </div>
</template>

<script>
import CarrouselComponent from "./components/CarrouselComponent";
export default {
  name: "app",
  components: { CarrouselComponent },
  data() {
    return {
      data: [
        {
          imageUrl: "https://source.unsplash.com/KJFKCed0YKo/1600x900",
          imageAlt: "",
          beds: 4,
          baths: 2,
          title: "Acogedora vivienda en pleno centro",
          // priceInCents: 190000,
          formattedPrice: "1.450€",
          reviewCount: 14,
          rating: 3.8
        },
        {
          imageUrl: "https://source.unsplash.com/tHkJAMcO3QE/1600x900",
          imageAlt: "",
          beds: 2,
          baths: 1,
          title: "Las mejores vistas de la ciudad",
          // priceInCents: 190000,
          formattedPrice: "1.900€",
          reviewCount: 38,
          rating: 4.2
        },
        {
          imageUrl: "https://source.unsplash.com/BZdv_I1LeLg/1600x900",
          imageAlt: "",
          beds: 4,
          baths: 2,
          title: "Apartamento con los mejores servicios",
          // priceInCents: 190000,
          formattedPrice: "1.200€",
          reviewCount: 24,
          rating: 4.5
        }
      ]
    };
  }
};
</script>

<style src="./assets/tailwind.css">
