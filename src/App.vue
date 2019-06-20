<template>
  <div class="app-root">
    <router-view />

    <!-- 禁用全局配色
    <VBtn small fab dark falt fixed top="top" right="right" class="setting-fab" color="red" @click="openThemeSettings">
      <v-icon>settings</v-icon>
    </VBtn>
    < setting drawer
    <v-navigation-drawer class="setting-drawer" temporary right v-model="rightDrawer" hide-overlay fixed>
      <theme-settings></theme-settings>
    </v-navigation-drawer>
    -->
    <!-- global snackbar -->
    <v-snackbar
      v-model="snackbar.show"
      :timeout="3000"
      bottom
      right
      :color="snackbar.color"
    >
      {{ snackbar.text }}
      <VBtn
        dark
        flat
        icon
        @click.native="snackbar.show = false"
      >
        <v-icon>close</v-icon>
      </VBtn>
    </v-snackbar>
  </div>
</template>

<script>
export default {
  components: {},
  data () {
    return {
      rightDrawer: false,
      snackbar: {
        show: false,
        text: '',
        color: ''
      }
    }
  },
  created () {
    // add app events
  },
  methods: {
    openThemeSettings () {
      this.$vuetify.goTo(0)
      this.rightDrawer = !this.rightDrawer
    }
  }
}
</script>

<style scoped>
.setting-fab {
  top: 50% !important;
  right: 0;
  border-radius: 0;
}
</style>
