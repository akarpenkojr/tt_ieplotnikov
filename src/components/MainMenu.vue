<template>
  <div class="mainMenu">
    <Hamburger />
  </div>
</template>

<script>
import Hamburger from "@/components/Hamburger.vue";

export default {
  name: "MainMenu",
  components: {
    Hamburger
  }
};
</script>

<style scoped lang="scss">
.mainMenu {
  align-self: center;
}
</style>
