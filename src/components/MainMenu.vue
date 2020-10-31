<template>
  <div class="mainMenu">
    <Hamburger
      :showMainMenu="showMainMenu"
      @click="switchMainMenu"
      class="mainMenu__hamburgerItem"
    />
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
@media screen and (min-width: 768px) {
  .mainMenu__hamburgerItem {
    display: none;
  }
}
</style>
