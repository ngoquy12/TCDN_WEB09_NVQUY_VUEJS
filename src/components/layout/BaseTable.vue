<template>
    <div class="m-body-table">
      <table class="m-table">
        <thead class="m-thead">
          <tr class="m-tr">
            <th class="m-th m-checkall">
              <label class="m-table-checkbox">
                <input type="checkbox" class="m-input-checkall" />
                <span class="m-checkbox">
                  <span class="m-checkbox-inner">
                    <div class="m-icon-16 m-icon-checkbox-active"></div>
                  </span>
                </span>
              </label>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 143px; width: 143px">
              <div class="m-th-title">Mã nhân viên</div>
            </th>
            <th class="m-th m-dynamic-col" style="min-width: 173px">
              <div class="m-th-title">Tên nhân viên</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 120px; width: 120px">
              <div class="m-th-title">Giới tính</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 145px; width: 145px">
              <div class="m-th-title m-th-title-dob">Ngày sinh</div>
            </th>
            <th
              class="m-th m-dynamic-col"
              style="min-width: 200px; width: 200px">
              <div class="m-th-title" title="Số chứng minh nhân dân">
                Số CMND
              </div>
            </th>
            <th
              class="m-th m-dynamoc-col"
              style="min-width: 122px; width: 122px">
              <div class="m-th-title">Chức danh</div>
            </th>
            <th class="m-th m-dynamic-col" style="min-width: 250px">
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
              class="m-th m-dynamic-col"
              style="min-width: 250px; width: 250px"
            >
              <div class="m-th-title">Chi nhánh</div>
            </th>
            <th class="m-th m-th-widget" style="width: 120px; min-width: 120px">
              <div class="m-th-title">Chức năng</div>
            </th>
          </tr>
        </thead>
        <tbody class="m-tbody">
          <!-- Dữ liệu cảu bảng sẽ được hiển thị ở đây sau khi append dữ liệu từ api -->
          <tr class="m-tr" v-for="(item, index) in employeeList" :key="index">
            <td class="m-td m-td-multi">
              <label class="m-table-checkbox">
                <input type="checkbox" class="m-input-checkbox" />
                <span class="m-checkbox">
                  <span class="m-checkbox-inner">
                    <div class="m-icon-16 m-icon-checkbox-active"></div>
                  </span>
                </span>
              </label>
            </td>
            <td class="m-td m-td-emp-code">{{item.EmployeeCode}}</td>
            <td class="m-td">{{item.EmployeeName}}</td>
            <td class="m-td">{{item.GenderName}}</td>
            <td class="m-td">{{item.DateOfBirth}}</td>
            <td class="m-td">{{item.EmployeePosition}}</td>
            <td class="m-td">{{item.IdentityNumber}}</td>
            <td class="m-td">{{item.DepartmentName}}</td>
            <td class="m-td">{{item.BankAccountNumber}}</td>
            <td class="m-td">{{item.BankName}}</td>
            <td class="m-td">{{item.BankBranchName}}</td>
            <td class="m-td">{{item.BankProvinceName}}</td>
            <td class="m-td m-td-widget">
              <div class="m-dropdown">
                <button class="m-dropdown-type-feature m-dropdown-btn-text m-edit-employee">
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
</template>
<script>
export default {
  name: "BaseTable",

  props: ["apiUrl"],
  //lay du lieu
  created() {
    fetch(this.apiUrl)
      .then(respone => respone.json())
      .then(respone => {
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