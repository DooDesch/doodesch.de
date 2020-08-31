<template lang="pug">
  v-row(justify="center" align="center" style="height: 100vh;")
    v-card.d-inline-block.mx-auto
      v-container
        v-row(justify='space-between')
          v-col(cols='auto')
            v-img(height='200' width='200' src='/doodesch.jpg').rounded-circle
          v-col.mx-6.text-center.pl-0(cols='auto')
            v-row.flex-column.ma-0.fill-height(justify='center')
              v-col.px-0
                v-icon mdi-cake
                div 25
              v-col.px-0
                v-icon mdi-human-male-height
                div 1.85
              v-col.px-0
                v-icon mdi-weight-lifter
                div 90
          v-col.text-center.pl-0(cols='auto')
            v-row.flex-column.ma-0.fill-height(justify='center')
              v-col.px-0
                v-row(align='center' justify='center').ma-0.fill-height.
                  Programmierer & Gamer
              v-col.px-0
                v-row(align='center' justify='center').ma-0.fill-height.
                  PHP / JS / LUA / PYTHON
              v-col.px-0
                v-row(align='center' justify='center').ma-0.fill-height.
                  Köln
</template>

<script>
export default {
  transition(to, from) {
    if (to.name === 'about') {
      return 'scroll-y-reverse-transition'
    } else {
      return 'scroll-y-transition'
    }
  },
}
</script>
