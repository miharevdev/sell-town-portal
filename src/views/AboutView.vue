<template>
  <div class="about">
    <div class="cont">
      <base-table
        control
        :fields="fields" 
        :table-data="tableData" 
        :slots="['button', 'delete']"
      >
        <template #button>
          <base-button title="Active" />
        </template>
        <template #delete>
          <base-button title="Delete" />
        </template>
      </base-table>
    </div>
  </div>
</template>

<script>
import BaseTable from "@/components/table/BaseTable.vue"
import BaseButton from "@/components/UI/button/BaseButton.vue";

  export default {
    components: {
      BaseTable,
      BaseButton
    },

    data() {
            return {
              fields: [
                { key: "id", cap: "ID", width: 120, dictionary:"" },
                { key: "name", cap: "Name", width: 220, dictionary:"" },
                { key: "date", cap: "Date", width: 100, dictionary:"" },
                {width: 160},
              ],

              tableData: [
                { id: 1, name: "Vasya", date: "10-02-23" },
                { id: 2, name: "Petya", date: "14-02-23" },
                { id: 3, name: "Sasha", date: "22-02-23" },
                { id: 4, name: "Vasya", date: "10-02-23" },
                { id: 5, name: "Petya", date: "14-02-23" },
                { id: 6, name: "Sasha", date: "22-02-23" },
                { id: 7, name: "Vasya", date: "10-02-23" },
                { id: 8, name: "Petya", date: "14-02-23" },
                { id: 9, name: "Sasha", date: "22-02-23" },
                { id: 10, name: "Vasya", date: "10-02-23" },
                { id: 11, name: "Petya", date: "14-02-23" },
                { id: 12, name: "Sasha", date: "22-02-23" },
                { id: 13, name: "Vasya", date: "10-02-23" },
                { id: 14, name: "Petya", date: "14-02-23" },
                { id: 15, name: "Sasha", date: "22-02-23" },
                { id: 16, name: "Vasya", date: "10-02-23" },
                { id: 17, name: "Petya", date: "14-02-23" },
                { id: 18, name: "Sasha", date: "22-02-23" },
                { id: 19, name: "Vasya", date: "10-02-23" },
                { id: 20, name: "Petya", date: "14-02-23" },
                { id: 21, name: "Sasha", date: "22-02-23" },
                { id: 22, name: "Vasya", date: "10-02-23" },
                { id: 23, name: "Petya", date: "14-02-23" },
                { id: 24, name: "Sasha", date: "22-02-23" },
              ]
            }
        },
  }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.cont {
  height: 60%;
  width: 100%;
}

.about {
  @include flex-col(flex-start, center);
  height: 100%;
  width: 100%;
}

.btn {
  margin-top: 4px;
}
</style>