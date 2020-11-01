<template>
  <div class="mainMenu">
    <Hamburger
      :showMainMenu="showMainMenu"
      @click="switchMainMenu"
      class="mainMenu__hamburgerItem"
    />
    <AccountingSection class="mainMenu__item" />
    <ReportsSection class="mainMenu__item" />
    <StaffSection class="mainMenu__item" />
    <MarketingSection class="mainMenu__item" />
    <BookmarksSection class="mainMenu__item" />
  </div>
</template>

<script>
import Hamburger from "@/components/Hamburger.vue";
import AccountingSection from "@/components/AccountingSection";
import BookmarksSection from "@/components/BookmarksSection";
import MarketingSection from "@/components/MarketingSection";
import ReportsSection from "@/components/ReportsSection";
import StaffSection from "@/components/StaffSection";

export default {
  name: "MainMenu",
  components: {
    Hamburger,
    AccountingSection,
    BookmarksSection,
    MarketingSection,
    ReportsSection,
    StaffSection
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
  display: flex;
  flex-direction: row;
}
.mainMenu__item {
  display: none;
}
.mainMenu__hamburgerItem {
  display: inline-block;
  margin-right: 25px;
}
@media screen and (min-width: 768px) {
  .mainMenu__hamburgerItem {
    display: none;
  }
  .mainMenu__item {
    display: inline-block;
    align-self: center;
    margin-right: 31px;
  }
}
@media screen and (min-width: 1024px) {
  .mainMenu {
    flex-direction: column;
    border-top: 1px solid #45484e;
    padding-top: 25px;
    width: 100%;
    &__item {
      margin-right: auto;
      margin-left: auto;
      margin-bottom: 33px;
    }
  }
}
</style>
