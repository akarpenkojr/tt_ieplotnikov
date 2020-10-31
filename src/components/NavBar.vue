<template>
  <div class="navBar">
    <MainMenu />
    <UserMenu />
  </div>
</template>

<script>
import MainMenu from "@/components/MainMenu.vue";
import UserMenu from "@/components/UserMenu.vue";

export default {
  components: {
    MainMenu,
    UserMenu
  },
  name: "NavBar",
  props: {
    msg: String
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

@media (min-width: 768px) {
  .navBar {
    padding-right: 30px;
    padding-left: 30px;
  }
}

@media (min-width: 1024px) {
  .navBar {
    width: 60px;
    height: 100vh;
    flex-direction: column;
  }
}
</style>
