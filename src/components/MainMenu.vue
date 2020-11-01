<template>
  <div class="mainMenu">
    <Hamburger
      :isShowedMainMenu="showMainMenuItems"
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
    showMainMenuItems: false
  }),
  methods: {
    switchMainMenu() {
      this.showMainMenuItems = !this.showMainMenuItems;
    }
  }
};
</script>

<style scoped lang="scss">
.mainMenu {
  align-self: center;
  display: flex;
  flex-direction: row;
  &__item {
    display: none;
    transition: opacity 0.175s ease;
    -webkit-transition: opacity 0.175s ease;
    -moz-transition: opacity 0.175s ease;
    -o-transition: opacity 0.175s ease;
    cursor: pointer;
    &:hover {
      opacity: 0.7;
    }
  }
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
    width: 34px;
    justify-items: flex-start;
    &__item {
      margin-right: auto;
      margin-left: auto;
      margin-bottom: 33px;
      &:nth-child(2) {
        margin-top: 25px;
      }
    }
  }
}
</style>
