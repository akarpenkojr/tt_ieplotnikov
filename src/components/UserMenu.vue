<template>
  <div class="userMenu">
    <div class="userMenu__minorSectionsWrapper">
      <OptionsSection class="userMenu__item userMenu__minorSectionItem" />
      <RulesSection class="userMenu__item userMenu__minorSectionItem" />
    </div>
    <div class="userMenu__profileSectionsWrapper">
      <NotificationsSection class="userMenu__item userMenu__notificationItem" />
      <ProfileSection class="userMenu__item" />
    </div>
  </div>
</template>

<script>
import RulesSection from "@/components/RulesSection";
import OptionsSection from "@/components/OptionsSection";
import NotificationsSection from "@/components/NotificationsSection";
import ProfileSection from "@/components/ProfileSection";

export default {
  name: "UserMenu",
  components: {
    RulesSection,
    OptionsSection,
    NotificationsSection,
    ProfileSection
  }
};
</script>

<style scoped lang="scss">
.userMenu {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: flex-end;
  align-self: center;
  width: 100%;
}
.userMenu__minorSectionsWrapper {
  margin-left: 0;
  margin-right: auto;
  align-self: center;
}
.userMenu__profileSectionsWrapper {
  align-self: center;
}
.userMenu__item {
  align-self: center;
  transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
  transition: opacity 0.175s ease;
  cursor: pointer;
}
.userMenu__item:hover {
  opacity: 0.7;
}
.userMenu__minorSectionItem {
  margin-left: 25px;
}
.userMenu__notificationItem {
  margin-right: 20px;
  margin-left: auto;
}
@media screen and (min-width: 768px) {
  .userMenu__minorSectionsWrapper {
    margin-left: auto;
    margin-right: 20px;
  }
}
</style>
