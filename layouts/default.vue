<template>
  <div class="bg-base" role="application">
    <Header class="z-20" />
    <GlobalNav
      class="transform lg:translate-x-0 transition duration-500 z-20"
      :class="[this.$store.state.isOpen ? 'translate-x-0' : 'translate-x-64']"
    />
    <transition name="fade">
      <Overlay v-if="this.$store.state.isOpen" class="z-10" />
    </transition>
    <main
      class="mt-24 lg:mr-64 transition duration-500"
      :class="{ 'overflow-hidden': this.$store.state.isOpen }"
    >
      <Nuxt />
    </main>
    <Footer class="-mt-10" />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import Header from '@/components/organisms/Header'
import GlobalNav from '@/components/organisms/GlobalNav'
import Overlay from '@/components/atoms/Overlay'
import Footer from '@/components/organisms/Footer'

export default {
  components: {
    Header,
    GlobalNav,
    Overlay,
    Footer,
  },
  computed: {
    ...mapGetters({
      isOpen: 'isOpen',
    }),
  },
  watch: {
    isOpen: {
      handler() {
        if (this.isOpen === true) {
          document.body.classList.add('overflow-y-hidden')
          document.addEventListener('touchmove', this.handleTouchMove, {
            passive: false,
          })
        } else {
          document.body.classList.remove('overflow-y-hidden')
          document.removeEventListener('touchmove', this.handleTouchMove, {
            passive: false,
          })
        }
      },
      deep: true,
    },
  },
  methods: {
    handleTouchMove(event) {
      event.preventDefault()
    },
  },
}
</script>

<style lang="postcss">
html {
  scroll-behavior: smooth;
}

body {
  background-color: #7b8e89;
}

.container {
  @apply mx-auto max-w-container;
}

.section {
  min-height: calc(100vh - 6rem);
  min-height: calc(calc(var(--vh, 1vh) * 100) - 6rem);
  @apply py-8 lg:py-16 w-full border-b border-secondary;
}

.flex-center {
  @apply items-center justify-center;
}

.h-main {
  height: calc(100vh - 6rem);
  height: calc(calc(var(--vh, 1vh) * 100) - 6rem);
}

.w-main {
  width: 100%;

  @media (min-width: 1024px) {
    width: calc(100vw - 16rem);
  }
}

.min-h-main {
  min-height: calc(100vh - 20rem);
  min-height: calc(calc(var(--vh, 1vh) * 100) - 20rem);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
