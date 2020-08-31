<template lang="pug">
  v-row.platform
    v-col.py-0
      v-row(align="center" justify="center" style="height: 100%").text-center
        v-btn(elevation="0" tile href="https://twitch.tv/doodesch" target="_blank")#twitch.platform--btn.
          <v-icon x-large>mdi-twitch</v-icon>
          twitch
    v-col.py-0
      v-row(align="center" justify="center" style="height: 100%").text-center
        v-btn(elevation="0" tile href="https://discord.doodesch.de" target="_blank")#discord.platform--btn.
          <v-icon x-large>mdi-discord</v-icon>
          discord
    v-col.py-0
      v-row(align="center" justify="center" style="height: 100%").text-center
        v-btn(elevation="0" tile href="https://steamcommunity.com/id/doodesch" target="_blank")#steam.platform--btn.
          <v-icon x-large>mdi-steam</v-icon>
          steam
</template>

<script>
export default {}
</script>

<style lang="scss">
#twitch {
  background-color: #6441a4aa;
  color: #fff;
}

#discord {
  background-color: #7289daaa;
  color: #fff;
}

#steam {
  background-color: #171a21aa;
  color: #fff;
}

.platform {
  height: 100vh;
  background: transparent;
  backdrop-filter: blur(5px);
}

.platform--btn {
  min-width: 240px !important;
  height: 100% !important;
  width: 100% !important;
}
</style>
