<template>
  <div>
    <!-- class chung -->
    <div class="m-container">
      <!-- Phần menu  -->
      <TheMenu />
      <!-- Phần content -->
      <div class="m-content">
        <!-- Phần navbar  -->
        <TheNavbar />
        <div class="m-main-content">
          <!-- header content  -->
          <TheContentHeader />
          <div class="m-content-body">
            <TheContentBody></TheContentBody>
            <!-- table gọi api danh sách nhân viên  -->
            <BaseTable apiUrl="https://amis.manhnv.net/api/v1/Employees" />
            <!-- Thanh phân trang  -->
            <ThePaging />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TheMenu from "./components/layout/TheMenu.vue";
import BaseTable from "./components/layout/BaseTable.vue";
import TheNavbar from "./components/layout/TheNavbar.vue";
import TheContentHeader from "./components/layout/TheContentHeader.vue";
import TheContentBody from "./components/layout/TheContentBody.vue";
import ThePaging from "./components/layout/ThePaging.vue";
export default {
  name: "App",
  components: {
    TheMenu,
    BaseTable,
    TheNavbar,
    TheContentHeader,
    TheContentBody,
    ThePaging,
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