<template>
  <div class="navBar" :class="{ 'navBar--isActive': isNavBarUnfolded }">
    <MainMenu class="navBar__mainMenu navBar__item" />
    <MinorMenu class="navBar__minorMenu navBar__item" />
    <UserMenu class="navBar__userMenu navBar__item" />
    <openMenuButtonIcon
      class="navBar__openMenuButtonIcon navBar__item"
      @click="switchNavBar"
    />
  </div>
</template>

<script>
import MainMenu from "@/components/MainMenu.vue";
import UserMenu from "@/components/UserMenu.vue";
import MinorMenu from "@/components/MinorMenu.vue";
import openMenuButtonIcon from "@/components/openMenuButtonIcon";

export default {
  components: {
    MainMenu,
    UserMenu,
    MinorMenu,
    openMenuButtonIcon
  },
  name: "NavBar",
  data: () => ({
    isNavBarUnfolded: false
  }),
  methods: {
    switchNavBar() {
      this.isNavBarUnfolded = !this.isNavBarUnfolded;
    }
  }
};
</script>

<style scoped lang="scss">
.navBar {
  height: 50px;
  width: 100%;
  display: flex;
  flex-direction: row;
  background-color: rgba(51, 51, 51, 1);
  padding-right: 20px;
  padding-left: 20px;
}
.navBar__openMenuButtonIcon {
  visibility: hidden;
}

@media screen and (min-width: 768px) {
  .navBar {
    padding-right: 30px;
    padding-left: 30px;
  }
}

@media screen and (min-width: 1024px) {
  .navBar {
    position: relative;
    padding: 0;
    width: 60px;
    height: 100vh;
    flex-direction: column;
    align-content: flex-start;
    transition: width 0.5s ease-in;
    -webkit-transition: width 0.5s ease-in;
    -moz-transition: width 0.5s ease-in;
    -o-transition: width 0.5s ease-in;
    &__item {
      margin-left: 13px;
      margin-right: auto;
    }
    &--isActive {
      width: 200px;
    }
    &__mainMenu {
      order: 2;
      margin-bottom: auto;
    }
    &__userMenu {
      order: 1;
    }
    &__mainMenu:before {
      content: "";
      border-bottom: 1px solid #45484e;
      width: 100%;
      position: absolute;
      left: 0;
    }
    &__minorMenu {
      order: 3;
    }
    &__openMenuButtonIcon {
      order: 4;
      visibility: visible;
      margin-top: 35px;
      margin-bottom: 35px;
    }
  }
}
</style>
