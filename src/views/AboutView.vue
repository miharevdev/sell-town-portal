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
                { key: "id", cap: "ID", show: true, width: 120, dictionary:"" },
                { key: "name", cap: "Name", show: true, width: 220, dictionary:"" },
                { key: "count", cap: "Count", show: true, width: 180, dictionary:"" },
                { key: "date", cap: "Date", show: true, width: 100, dictionary:"" },
                {width: 150},
              ],

              tableData: [
                { id: 1, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 2, name: "Petya", count: 30, date: "14-02-23" },
                { id: 3, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 4, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 5, name: "Petya", count: 30, date: "14-02-23" },
                { id: 6, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 7, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 8, name: "Petya", count: 30, date: "14-02-23" },
                { id: 9, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 10, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 11, name: "Petya", count: 30, date: "14-02-23" },
                { id: 12, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 13, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 14, name: "Petya", count: 30, date: "14-02-23" },
                { id: 15, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 16, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 17, name: "Petya", count: 30, date: "14-02-23" },
                { id: 18, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 19, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 20, name: "Petya", count: 30, date: "14-02-23" },
                { id: 21, name: "Sasha", count: 20, date: "22-02-23" },
                { id: 22, name: "Vasya", count: 10, date: "10-02-23" },
                { id: 23, name: "Petya", count: 30, date: "14-02-23" },
                { id: 24, name: "Sasha", count: 20, date: "22-02-23" },
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