<template>
  <div class="about">
    <base-select title="Выбрать" :select-data="options" />
    <base-select title="Выбрать" :select-data="options" />
    <base-select title="Выбрать" :select-data="options" />
    <base-input title="Найти" hasLeftTitile />
    
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
          { id: 10, name:"option 10" }
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