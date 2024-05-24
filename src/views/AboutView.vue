<template>
  <div class="about">
    <base-select title="Открыть" :options="options" />
    <base-button title="Открыть" class="btn" />
    <base-input title="Открыть" />
    <base-input title="Открыть" hasLeftTitile />
    <base-button class="btn" />
    <base-button class="btn" />
  </div>
</template>

<script>
import BaseSelect from "@/components/UI/select/base-select/BaseSelect.vue";
import BaseButton from "@/components/UI/button/BaseButton.vue"
import BaseInput from "@/components/UI/input/BaseInput.vue";


  export default {
    components: {
      BaseButton,
      BaseSelect,
      BaseInput
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
  @include flex-row(flex-start, center);
  flex-wrap: wrap;
}

.btn {
  margin-top: 4px;
}
</style>