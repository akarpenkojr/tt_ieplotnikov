<template>
  <div class="navBar">
    <MainMenu class="navBar__mainMenu" />
    <MinorMenu class="navBar__minorMenu" />
    <UserMenu class="navBar__userMenu" />
  </div>
</template>

<script>
import MainMenu from "@/components/MainMenu.vue";
import UserMenu from "@/components/UserMenu.vue";
import MinorMenu from "@/components/MinorMenu.vue";

export default {
  components: {
    MainMenu,
    UserMenu,
    MinorMenu
  },
  name: "NavBar"
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

@media screen and (min-width: 768px) {
  .navBar {
    padding-right: 30px;
    padding-left: 30px;
  }
}

@media screen and (min-width: 1024px) {
  .navBar {
    padding: 0;
    width: 60px;
    height: 100vh;
    flex-direction: column;
    align-content: flex-start;
    &__mainMenu {
      order: 2;
      margin-bottom: auto;
    }
    &__userMenu {
      order: 1;
    }
    &__minorMenu {
      order: 3;
    }
  }
}
</style>
