<template>
  <nav
    class="h-screen w-64 fixed top-24 bottom-0 right-0 overflow-y-auto bg-primary"
  >
    <div class="w-32 h-32 mx-auto border flex flex-center mt-8">
      <h1 class="text-center text-white text-2xl font-extralight">Index</h1>
    </div>
    <ul class="mb-24 mt-8">
      <li
        v-for="(item, index) in nav"
        :key="index"
        class="text-center text-white text-2xl font-extralight hover:bg-secondary transition duration-500"
        @click="close()"
      >
        <nuxt-link v-scroll-to="'#' + item" to class="block py-8">{{
          item
        }}</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  data() {
    return {
      nav: ['profile', 'works', 'links'],
    }
  },
  methods: {
    ...mapMutations({
      close: 'close',
    }),
  },
}
</script>
