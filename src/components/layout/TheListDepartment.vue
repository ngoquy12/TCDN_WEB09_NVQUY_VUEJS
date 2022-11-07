<template >
    <div>
        <div class="m-combo-menu" >
            <div class="m-combo-menu-header">
                <table class="m-menu-table">
                    <thead class="m-menu-header">
                        <tr>
                            <th class="m-menu-header-th" style="width: 100px; text-align: left"><span>Mã đơn vị</span></th>
                            <th class="m-menu-header-th" style="width: 250px; text-align: left"><span>Tên đơn vị</span></th>
                        </tr>
                    </thead>
                </table>
            </div>
            <div class="m-combo-menu-content">
                <table class="m-menu-table">
                    <tbody class="m-menu-items m-departments-list">
                        <tr class="m-menu-items-tr" v-for="(item, index) in departmentList" :key="index">
                            <td class="m-menu-items-td" style="width: 100px; text-align: left"><span>{{item.DepartmentCode}}</span></td>
                            <td class="m-menu-items-td" style="width: 250px; text-align: left"><span>{{item.DepartmentName}}</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name : "TheListDepartment",
    props :["apiDepartments"],
    methods:{
        
    },
    //lay du lieu
  created() {
    fetch(this.apiDepartments)
      .then((respone) => respone.json())
      .then((respone) => {
        this.departmentList = respone;
      });
  },
    data(){
        return {
            departmentList:[]
        }
    }
}
</script>
