<template>
  <div class="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import "~/src/assets/styles/custom.scss";

.app {
  @include flex-row(center, center);
  height: 100vh;
  width: 100vw;
}

</style>
