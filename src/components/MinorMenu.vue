<template>
  <div class="minorMenu">
    <OptionsSection class="minorMenu__item minorMenu__optionSectionItem" />
    <RulesSection class="minorMenu__item minorMenu__rulesSectionItem" />
  </div>
</template>

<script>
import RulesSection from "@/components/RulesSection";
import OptionsSection from "@/components/OptionsSection";

export default {
  name: "MinorMenu",
  components: {
    RulesSection,
    OptionsSection
  }
};
</script>

<style scoped lang="scss">
.minorMenu {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: flex-end;
  align-self: center;
  width: 100%;
  &__item {
    align-self: center;
    transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
    transition: opacity 0.175s ease;
    cursor: pointer;
    margin-right: 25px;
  }
  &__item:hover {
    opacity: 0.7;
  }
}

@media screen and (min-width: 1024px) {
  .minorMenu {
    flex-direction: column;
    width: auto;
    &__item {
      margin-right: auto;
      margin-left: auto;
    }
    &__rulesSectionItem {
      margin-bottom: 83px;
      margin-top: 25px;
    }
  }
}
</style>
