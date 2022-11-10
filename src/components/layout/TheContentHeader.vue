<template>
  <div>
    <div class="m-content-header">
      <div class="m-header-title">Nhân viên</div>
      <TheButton
        @click="showFormEmployee"
        title="Thêm mới nhân viên"
      ></TheButton>
    </div>
    <ThePopup v-if="isShow" />
    <TheLoading />
  </div>
</template>
<script>
import ThePopup from "./ThePopup.vue";
import TheButton from "../base/Button.vue";
import TheLoading from "../base/Loading.vue";
export default {
  name: "TheContentHeader",
  components: {
    ThePopup,
    TheButton,
    TheLoading,
  },
  props: [],
  methods: {
    showFormEmployee() {
      this.isShow = !this.isShow;
    },
  },
  data() {
    return {
      isShow: false,
    };
  },
};
</script>
  
<style scoped>
</style>