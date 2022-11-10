<template>
  <div>
    <div class="m-body-table">
      <table class="m-table">
        <thead class="m-thead">
          <tr class="m-tr">
            <th class="m-th m-checkall">
              <label class="m-table-checkbox">
                <TheCheckbox/>
              </label>
            </th>
            <th
              class="m-th m-dynamic-col" style="min-width: 143px; width: 143px">
              <div class="m-th-title">Mã nhân viên</div>
            </th>
            <th class="m-th m-dynamic-col" style="min-width: 150px">
              <div class="m-th-title">Tên nhân viên</div>
            </th>
            <th
              class="m-th m-dynamic-col" style="min-width: 120px; width: 120px">
              <div class="m-th-title">Giới tính</div>
            </th>
            <th
              class="m-th m-dynamic-col" style="min-width: 160px; width: 160px">
              <div class="m-th-title m-th-title-dob">Ngày sinh</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 206px; width: 206px">
              <div class="m-th-title" title="Số chứng minh nhân dân">
                Số CMND
              </div>
            </th>
            <th
              class="m-th m-dynamoc-col"
              style="min-width: 240px; width: 240px">
              <div class="m-th-title">Chức danh</div>
            </th>
            <th class="m-th m-dynamic-col" style="min-width: 200px">
              <div class="m-th-title">Tên đơn vị</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 150px; width: 150px">
              <div class="m-th-title">Số tài khoản</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 250px; width: 250px">
              <div class="m-th-title">Tên ngân hàng</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 250px; width: 250px">
              <div class="m-th-title" title="Chi nhánh tài khoản ngân hàng">
                Chi nhánh TK ngân hàng
              </div>
            </th>
            <th
              class="m-th m-th-widget m-th-title-fc"
              style="width: 140px; min-width: 140px">
              <div class="m-th-title">Chức năng</div>
            </th>
          </tr>
        </thead>
        <tbody class="m-tbody">
          <!-- Dữ liệu cảu bảng sẽ được hiển thị ở đây sau khi append dữ liệu từ api -->
          <tr class="m-tr" v-for="(item, index) in employeeList" :key="index">
            <td class="m-td m-td-multi">
              <label class="m-table-checkbox">
                <TheCheckbox />
              </label>
            </td>
            <td class="m-td m-td-emp-code">{{ item.EmployeeCode }}</td>
            <td class="m-td">{{ item.EmployeeName }}</td>
            <td class="m-td">{{ item.GenderName }}</td>
            <td class="m-td" style="text-align: center">
              {{ fomatDate(item.DateOfBirth) }}
            </td>
            <td class="m-td">{{ item.IdentityNumber }}</td>
            <td class="m-td">{{ item.ContactTitle }}</td>
            <td class="m-td">{{ item.DepartmentID }}</td>
            <td class="m-td">{{ item.BankAccount }}</td>
            <td class="m-td">{{ item.BankName }}</td>
            <td class="m-td">{{ item.BankBranchName }}</td>
            <td class="m-td m-td-widget">
              <div class="m-dropdown">
                <button
                    class="m-dropdown-type-feature m-dropdown-btn-text m-edit-employe">
                    <div class="m-btn-text">Sửa</div>
                </button>
                <button
                    class=" m-dropdown-type-feature m-dropdown-btn-ico m-dropdown-icon-emp">
                    <div class="m-btn-text">
                      <div class="m-icon-16 m-icon-arrow-down-blue"></div>
                    </div>
                </button>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script>
import TheCheckbox from "../base/Checkbox.vue";
export default {
  name: "BaseTable",
  components: {
    TheCheckbox,
  },
  props: ["apiUrl"],
  methods: {
    //Định dạng ngày/tháng/năm
    fomatDate(dob) {
      if (dob) {
        dob = new Date(dob);
        // Lấy ngày
        let date = dob.getDate();
        date = date < 10 ? `0${date}` : date;
        // Lấy tháng
        let month = dob.getMonth() + 1;
        month = month < 10 ? `0${month}` : month;
        // Lấy năm
        let year = dob.getFullYear();
        dob = `${date}/${month}/${year}`;
        return dob;
      }
      return "";
    },
  },
  //lay du lieu
  created() {
    fetch(this.apiUrl)
      .then((respone) => respone.json())
      .then((respone) => {
        this.employeeList = respone;
      });
  },
  data() {
    return {
      employeeList: [],
    };
  },
};
</script>
<style  scoped>
</style>