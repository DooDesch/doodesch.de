<template lang="pug">
  v-app(dark)
    transition(name='fade')
      div(v-if="!about")#background
    v-main.pb-0
      v-container(fluid).py-0
        nuxt.

    v-footer(v-if="about" :absolute='!fixed' app)
      span © {{ new Date().getFullYear() }}
    v-btn(v-if="about" large fab elevation='16' to='/')#back.mt-6 
      v-icon mdi-chevron-up
    v-btn(v-else large fab elevation='16' to='about')#next.mb-6 
      v-icon mdi-chevron-down
</template>

<script>
export default {
  data() {
    return {
      fixed: true,
    }
  },
  computed: {
    about() {
      if (this.$route.name === 'about') return true
      return false
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
