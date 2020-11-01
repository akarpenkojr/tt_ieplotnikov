<template>
  <div class="userMenu">
    <NotificationsSection class="userMenu__item userMenu__notificationItem" />
    <ProfileSection class="userMenu__item userMenu__profileItem" />
  </div>
</template>

<script>
import NotificationsSection from "@/components/NotificationsSection";
import ProfileSection from "@/components/ProfileSection";

export default {
  name: "UserMenu",
  components: {
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
.userMenu__notificationItem {
  margin-right: 25px;
}
@media screen and (min-width: 1024px) {
  .userMenu {
    flex-direction: column;
    justify-content: flex-start;
    width: 34px;
    &__item {
      margin-right: auto;
      margin-left: auto;
    }
    &__profileItem {
      order: 1;
      margin-top: 13px;
      margin-bottom: 20px;
    }
    &__notificationItem {
      order: 2;
      margin-bottom: 17px;
    }
  }
}
</style>
