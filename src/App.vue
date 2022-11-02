<template>
  <div>
    <div class="m-container">
      <TheMenu></TheMenu>
     <BaseTable apiUrl="https://amis.manhnv.net/api/v1/Employees"></BaseTable>
    </div>

  </div>
</template>

<script>
import TheMenu from "./components/layout/TheMenu.vue";
import BaseTable from "./components/layout/BaseTable.vue"
export default {
  name: "App",
  components: {
    TheMenu,
    BaseTable
  },
  methods: {},
  data() {
    return {
      employeeList: [],
    };
  },
};
</script>

<style>
@import url(./css/main.css);
</style>