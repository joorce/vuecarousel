<template>
  <div class="bg-white rounded-lg overflow-hidden shadow-lg border border-gray-200">
    <div class="relative bg-white pb-2/3">
      <img
        class="absolute w-full h-full object-cover object-bottom"
        :src="images[currentIndex].imageUrl"
        :alt="images[currentIndex].imageAlt"
      />
      <span class>
        <a href="#" @click.prevent="nextImage">
          <svg
            class="absolute icon-right fill-current"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
          >
            <path
              d="M10 0a10 10 0 1 1 0 20 10 10 0 0 1 0-20zM2 10a8 8 0 1 0 16 0 8 8 0 0 0-16 0zm10.54.7L9 14.25l-1.41-1.41L10.4 10 7.6 7.17 9 5.76 13.24 10l-.7.7z"
            />
          </svg>
        </a>
        <a href="#" @click.prevent="prevImage">
          <svg
            class="absolute icon-left fill-current"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
          >
            <path
              d="M10 20a10 10 0 1 1 0-20 10 10 0 0 1 0 20zm8-10a8 8 0 1 0-16 0 8 8 0 0 0 16 0zM7.46 9.3L11 5.75l1.41 1.41L9.6 10l2.82 2.83L11 14.24 6.76 10l.7-.7z"
            />
          </svg>
        </a>
      </span>
    </div>
    <div class="p-6">
      <div class="flex items-baseline">
        <span
          class="text-xs font-semibold uppercase tracking-wide text-teal-700 bg-teal-200 rounded-full px-2 inline-block"
        >Novedad</span>
        <div
          class="text-xs text-gray-600 uppercase tracking-wide ml-1"
        >{{ images[currentIndex].beds }} dormitorios &bull; {{ images[currentIndex].baths }} baños</div>
      </div>
      <h4 class="text-lg font-semibold leading-tight truncate mt-1">{{ images[currentIndex].title }}</h4>
      <div class="mt-1">
        {{ images[currentIndex].formattedPrice }}
        <span class="text-gray-600 text-sm">/ semana</span>
      </div>
      <div class="mt-2 flex items-center">
        <svg
          v-for="i in 5"
          :key="i"
          :class="i <= images[currentIndex].rating ? 'text-teal-500' : 'text-gray-300'"
          class="h-4 w-4 fill-current"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M8.133 20.333c-1.147.628-2.488-.387-2.269-1.718l.739-4.488-3.13-3.178c-.927-.943-.415-2.585.867-2.78l4.324-.654 1.934-4.083a1.536 1.536 0 0 1 2.804 0l1.934 4.083 4.324.655c1.282.194 1.794 1.836.866 2.78l-3.129 3.177.739 4.488c.219 1.331-1.122 2.346-2.269 1.718L12 18.214l-3.867 2.119z"
            fill-rule="evenodd"
          />
        </svg>
        <span class="text-gray-600 text-sm ml-1">{{ images[currentIndex].reviewCount }} reseñas</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "carrousel-component",
  props: ["images"],
  data() {
    return {
      currentIndex: 0,
      currentItem: this.images[this.currentIndex]
    };
  },
  methods: {
    nextImage() {
      this.currentIndex++;
      if (this.currentIndex == this.images.length) {
        this.currentIndex = 0;
      }
    },
    prevImage() {
      this.currentIndex--;
      if (this.currentIndex < 0) {
        this.currentIndex = this.images.length - 1;
      }
    }
  }
};
</script>

<style>
@import url(../assets/tailwind.css);
.pb-2\/3 {
  padding-bottom: 66%;
}

.icon-right {
  height: 36px;
  top: calc(55% - 36px);
  right: 8px;
  color: white;
  /* bottom: 50%; */
  /* z-index: 10; */
}
.icon-left {
  height: 36px;
  top: calc(55% - 36px);
  left: 8px;
  color: white;
  opacity: 0.85;
  /* bottom: 50%; */
  /* z-index: 10; */
}
.icon-left:hover {
  color: red;
}
.icon-right:hover {
  color: red;
}
</style>

