<template>
    <div>
        <div class="m-body-toolbar">
            <div class="m-body-toolbar-left">
                <button id="m-input-delete" class="m-button " disabled>
                    <div class="m-button-text">Xóa</div>
                </button>
            </div>
            <div class="m-body-toolbar-right">
                <div class="m-search-area">
                    <input type="text" class="m-input m-input-icon m-input-search m-search-emp"
                        placeholder="Tìm theo mã, tên nhân viên" />
                    <div class="m-icon-after m-icon-16 m-icon-search" title="Tìm kiếm"></div>
                </div>
                <div class="m-refresh-button m-icon-24 m-icon-refresh" title="Lấy lại dữ liệu"></div>
            </div>
        </div>
    </div>
  </template>
  <script>
  export default {
    name: "TheContentBody",
    props: [],
    methods: {},
    data() {
      return {};
    },
  };
  </script>
    
  <style scoped>
  </style>