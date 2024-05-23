<template>
  <div class="about">
    <base-input title="Найти"  />
    <base-select title="Выбрать" :select-data="options" />
  </div>
</template>

<script>
import BaseInput from "@/components/UI/input/BaseInput.vue";
import BaseSelect from "@/components/UI/select/base-select/BaseSelect.vue";

  export default {
    components: {
      BaseInput,
      BaseSelect
    },

    data() {
      return {
        options: [
          { id: 1, name:"option 1" },
          { id: 2, name:"option 2" },
          { id: 3, name:"option 3" },
          { id: 4, name:"option 4" },
          { id: 5, name:"option 5" },
          { id: 6, name:"option 6" },
          { id: 7, name:"option 7" },
          { id: 8, name:"option 8" },
          { id: 9, name:"option 9" },
          { id: 10, name:"option 10" },
          // { id: 11, name:"option 1" },
          // { id: 12, name:"option 2" },
          // { id: 13, name:"option 3" },
          // { id: 14, name:"option 4" },
          // { id: 15, name:"option 5" },
          // { id: 16, name:"option 1" },
          // { id: 17, name:"option 2" },
          // { id: 18, name:"option 3" },
          // { id: 19, name:"option 4" },
          // { id: 20, name:"option 5" },
        ]
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";


.about {
  @include flex-row(center, flex-start);
}
</style>