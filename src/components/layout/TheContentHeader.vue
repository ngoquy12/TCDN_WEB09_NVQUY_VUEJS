<template>
  <div>
    <div class="m-content-header">
      <div class="m-header-title">Nhân viên</div>
      <TheButton title="Thêm mới nhân viên" @click="showFormEmployee=true"/>
    </div>
    <ThePopup ></ThePopup>
  </div>
</template>
<script>
import ThePopup from "./ThePopup.vue";
 import TheButton from "../base/Button.vue"
export default {
  name: "TheContentHeader",
  components:{
    ThePopup,TheButton
    
  },
  props: [],
  methods: {
   
  },
  data() {
    return {
      showFormEmployee: false
    };
  },
};
</script>
  
<style scoped>

</style>