<template>
  <div>
    <div class="m-container">
      <TheMenu/>
      <div class="m-content">
        <TheNavbar></TheNavbar>
        <div class="m-main-content">
          <TheContentHeader></TheContentHeader>
          <div class="m-content-body">
            <TheContentBody></TheContentBody>
            <BaseTable apiUrl="https://amis.manhnv.net/api/v1/Employees"></BaseTable>
            <ThePaging></ThePaging>
          </div>

        </div>
      </div>
      
    </div>

  </div>
</template>

<script>
import TheMenu from "./components/layout/TheMenu.vue";
import BaseTable from "./components/layout/BaseTable.vue";
import TheNavbar from "./components/layout/TheNavbar.vue"
import TheContentHeader from "./components/layout/TheContentHeader.vue"
import TheContentBody from "./components/layout/TheContentBody.vue"
import ThePaging from "./components/layout/ThePaging.vue"
export default {
  name: "App",
  components: {
    TheMenu,
    BaseTable,
    TheNavbar,
    TheContentHeader,
    TheContentBody,
    ThePaging
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