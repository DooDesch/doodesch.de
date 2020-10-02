<template lang="pug">
  v-app(dark)
    transition(name='fade')
      div(v-if="!about")#background
    v-main.pb-0
      v-container(fluid).py-0
        nuxt.

    v-footer(v-if="about" :absolute='!fixed' app)
      span © {{ new Date().getFullYear() }}
    v-btn(v-if="about" x-large icon elevation='4' to='/')#back.mt-6
      v-icon mdi-chevron-up
    v-btn(v-else x-large icon elevation='4' to='about')#next.mb-6
      v-icon mdi-chevron-down
</template>

<script>
export default {
  data() {
    return {
      fixed: true,
      changing: false,
    }
  },
  computed: {
    about() {
      if (this.$route.name === 'about') return true
      return false
    },
  },
  beforeMount() {
    window.addEventListener('wheel', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('wheel', this.handleScroll)
  },
  methods: {
    async handleScroll(event) {
      if (!this.changing) {
        this.changing = true

        if (event.deltaY > 0) {
          await this.$router.push({ path: '/about' })
        } else {
          await this.$router.push({ path: '/' })
        }

        setTimeout(() => {
          this.changing = false
        }, 500)
      }
      // Your scroll handling here
    },
  },
}
</script>

<style lang="scss">
html {
  overflow: hidden;
}

#background {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-image: url('~@/static/background.jpg');
  background-position: center center;
}

#footer {
  background-color: rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(6px);
}

#next {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%);
}

#back {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%);
}
</style>
