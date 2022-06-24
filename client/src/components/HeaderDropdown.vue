<template>
  <div class="main-menu-container">
    <button class="button hamburger-button" @click="toggleMainMenu">
      <i class="fa-solid fa-bars"></i>
    </button>
    <ul class="main-menu-panel" :class="{ 'main-menu-open': mainMenuOpen }">
      <router-link to="../About Us" tag="li" class="main-menu-item"
        >About Us</router-link
      >

      <li class="sub-menu-container">
        <router-link
          to="../Community"
          class="main-menu-item sub sub-menu-button"
          >Categories</router-link
        >
        <ul class="sub-menu-panel">
          <router-link to="../About Us" tag="li" class="sub-menu-item"
            >Classics</router-link
          >
          <router-link to="../category/classics" tag="li" class="sub-menu-item"
            >Fantasy</router-link
          >
          <router-link to="../Community" tag="li" class="sub-menu-item"
            >Wellness</router-link
          >
          <router-link to="../Shipping" tag="li" class="sub-menu-item"
            >Comedy</router-link
          >
          <router-link to="../Contact Us" tag="li" class="sub-menu-item"
            >Romance</router-link
          >
        </ul>
      </li>
      <router-link to="../Community" tag="li" class="main-menu-item"
        >Community</router-link
      >
      <router-link to="../Shipping" tag="li" class="main-menu-item"
        >Shipping</router-link
      >
      <router-link to="../Contact Us" tag="li" class="main-menu-item"
        >Contact Us</router-link
      >
    </ul>
  </div>
</template>

<script>
export default {
  name: "HeaderDropdownMenu",
  data: function () {
    return {
      mainMenuOpen: false,
    };
  },
  methods: {
    toggleMainMenu() {
      this.mainMenuOpen = !this.mainMenuOpen;
    },
  },
};
</script>

<style scoped>
.main-menu-container {
  position: relative;
  align-self: center;
}

.main-menu-panel {
  position: absolute;
  right: -1rem;
  transform: translateX(100%);
  transition-duration: 300ms;
  transition-property: transform;
  transition-timing-function: ease-in-out;
  background-color: var(--neutral-color);
  color: var(--default-text-color);
  cursor: pointer;
}

.main-menu-panel.main-menu-open {
  transform: translate(0);
  opacity: 96%;
  z-index: 1;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.25);
}

.main-menu-item {
  display: inline-block;
  width: 100%;
  height: 100%;
  padding: 0.8em 2em;
  white-space: nowrap;
  text-decoration: none;
}

.main-menu-item:hover {
  background-color: var(--primary-color);
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.25);
  font-weight: 900;
}

.hamburger-button {
  background-color: var(--primary-background-color);
  border: none;
}

.hamburger-button:hover,
.hamburger-button:active {
  background: var(--primary-color);
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.25);
}

a,
a:active,
a:hover,
a:visited {
  color: var(--default-text-color);
  text-decoration: none;
}

.sub-menu-panel {
  background-color: silver;
}

.sub-menu-item {
  display: inline-block;
  width: 100%;
  height: 100%;
  padding: 0.4em 2em;
  white-space: nowrap;
  text-decoration: none;
}

.sub-menu-item:hover {
  background-color: orange;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.25);
  font-weight: 900;
}
</style>
