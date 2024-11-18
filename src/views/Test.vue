<script>

import Menu from '../components/Menu.vue';

export default {

  components: {
    Menu
  },

  data() {
    return {
      show: false
    }
  },

  methods: {
    toggleMenu() {
      this.show = !this.show;
      console.group('Test.vue => toggleMenu');
      console.log('show value', this.show);
      console.groupEnd();
    }
  }

}
</script>

<template>
  <div class="test">
    <h1>This is a Test page</h1>

    <button type="button" v-on:click="toggleMenu">Menu</button>
    <Transition name="menuTransition">
      <Menu v-if="show" />
    </Transition>
  </div>
</template>

<style>
/* @media (min-width: 1024px) {
  .test {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
} */

.menuTransition-enter-from,
.menuTransition-leave-to {
  opacity: 0;
}

.menuTransition-enter-active,
.menuTransition-leave-active {
  transition: opacity 0.5s ease;
}
</style>
