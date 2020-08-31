<template lang="pug">
  v-app(dark)#background
    v-main.pb-0
      v-container(fluid).py-0
        transition(name="scroll-y-transition" mode="out-in")
          nuxt.

    v-btn(large fab elevation="16" to="about")#next.mb-6 
      v-icon mdi-chevron-down
</template>

<script>
export default {}
</script>
