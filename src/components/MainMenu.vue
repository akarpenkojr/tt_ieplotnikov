<template>
  <div class="mainMenu">
    <Hamburger :showMainMenu="showMainMenu" @click="switchMainMenu" />
  </div>
</template>

<script>
import Hamburger from "@/components/Hamburger.vue";

export default {
  name: "MainMenu",
  components: {
    Hamburger
  },
  data: () => ({
    showMainMenu: false
  }),
  methods: {
    switchMainMenu() {
      this.showMainMenu = !this.showMainMenu;
    }
  }
};
</script>

<style scoped lang="scss">
.mainMenu {
  align-self: center;
}
</style>
