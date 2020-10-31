<template>
  <div
    class="hamburger hamburger--squeeze"
    :class="{ 'is-active': this.showMainMenu }"
  >
    <div class="hamburger-box">
      <div class="hamburger-inner"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hamburger",
  props: {
    showMainMenu: {
      type: Boolean
    }
  },
  data: () => ({}),
  methods: {}
};
</script>

<style scoped lang="scss">
.hamburger {
  display: inline-block;
  cursor: pointer;
  transition-property: opacity, filter;
  transition-duration: 0.15s;
  transition-timing-function: linear;
  font: inherit;
  color: #8e9cbb;
  text-transform: none;
  background-color: transparent;
  border: 0;
  margin: 0;
  overflow: visible;
}
.hamburger:hover {
  opacity: 0.7;
}
.hamburger.is-active:hover {
  opacity: 0.7;
}
.hamburger.is-active .hamburger-inner,
.hamburger.is-active .hamburger-inner::before,
.hamburger.is-active .hamburger-inner::after {
  background-color: #8e9cbb;
}

.hamburger-box {
  width: 16px;
  height: 10px;
  display: inline-block;
  position: relative;
}
.hamburger-inner {
  display: block;
  top: 50%;
  transform: translateY(-50%);
}
.hamburger-inner,
.hamburger-inner::before,
.hamburger-inner::after {
  width: 16px;
  height: 2px;
  background-color: #8e9cbb;
  border-radius: 2px;
  position: absolute;
  transition-property: transform;
  transition-duration: 0.35s;
  transition-timing-function: ease;
}
.hamburger-inner::before,
.hamburger-inner::after {
  content: "";
  display: block;
}
.hamburger-inner::before {
  top: -6px;
}
.hamburger-inner::after {
  bottom: -6px;
}
.hamburger--squeeze .hamburger-inner {
  transition-duration: 0.175s;
  transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
}
.hamburger--squeeze .hamburger-inner::before {
  transition: top 0.175s 0.12s ease, opacity 0.175s ease;
}
.hamburger--squeeze .hamburger-inner::after {
  transition: bottom 0.175s 0.12s ease,
    transform 0.175s cubic-bezier(0.55, 0.055, 0.675, 0.19);
}

.hamburger--squeeze.is-active .hamburger-inner {
  background-color: #ff238d;
  transform: rotate(45deg);
  transition-delay: 0.12s;
  transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
}
.hamburger--squeeze.is-active .hamburger-inner::before {
  background-color: #ff238d;
  top: 0;
  opacity: 0;
  transition: top 0.175s ease, opacity 0.175s 0.12s ease;
}
.hamburger--squeeze.is-active .hamburger-inner::after {
  background-color: #ff238d;
  bottom: 0;
  transform: rotate(-90deg);
  transition: bottom 0.175s ease,
    transform 0.175s 0.12s cubic-bezier(0.215, 0.61, 0.355, 1);
}
</style>
