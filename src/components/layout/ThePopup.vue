<template>
    <div>
        <div class="m-popup m-add-popup " v-show="isShow" >
            <div class="m-popup-con">
                <div class="m-popup-background"></div>
                <div class="m-popup-drag">
                    <div class="m-popup m-popup-content">
                        <div class="m-popup--header">
                            <div class="m-popup--title">
                                <div class="m-title">Thông tin nhân viên</div>
                                <label class="m-popup-checkbox">
                                   <TheCheckbox/>
                                    <span class="m-input-checkbox-label">Là khách hàng</span>
                                </label>
                                <label class="m-popup-checkbox">
                                    <TheCheckbox/>
                                    <span class="m-input-checkbox-label">Là nhà cung cấp</span>
                                </label>
                            </div>
                            <div class="m-popup--close">
                                <div class="m-icon-24 m-icon-help" style="margin-right: 6px" title="Trợ giúp"></div>
                                <div class="m-icon-24 m-icon-close m-close-add-popup" @click="hiddenFormEmployee">
                                </div>
                            </div>
                        </div>
                        <div class="m-popup--content">
                            <div class="m-popup--content-scroll">
                                <form id="employeeForm">
                                    <div class="m-content-2-col">
                                        <div class="m-col-1 m-flex-wrap">
                                            <div class="m-input-40 m-pr-6 m-pb-24">
                                                <div class="m-flex">
                                                    <TheLable lable="Mã"></TheLable>
                                                    <div class="m-input-title-require">&nbsp;*</div>
                                                </div>
                                                <input type="text" class="m-input m-input-require m-input-code" required
                                                    name="EmployeeCode" maxlength="25" propName="EmployeeCode"
                                                    tabindex="1" />
                                                <div class="m-input-message-error">&lt;Mã&gt;không được để trống</div>
                                            </div>
                                            <div class="m-input-60 m-pb-24">
                                                <div class="m-flex">
                                                    <TheLable lable="Tên"></TheLable>
                                                    <div class="m-input-title-require">&nbsp;*</div>
                                                </div>
                                                <input type="text" class="m-input m-input-require" required
                                                    name="EmployeeName" maxlength="128" propName="EmployeeName"
                                                    tabindex="2" />
                                                <div class="m-input-message-error">&lt;Tên&gt;không được để trống</div>
                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex">
                                                    <TheLable lable="Đơn vị"></TheLable>
                                                    <div class="m-input-title-require">&nbsp;*</div>
                                                </div>
                                                <div class="m-combo-box ">
                                                    <div class="m-combo-main-content m-input-error">
                                                        <div class="m-selected-options ">
                                                            <input type="hidden" name="DepartmentId"
                                                                propName="DepartmentId" />
                                                            <input type="text" class="m-combo-input " required
                                                                name="DepartmentName" propName="DepartmentName"
                                                                tabindex="7" />
                                                        </div>
                                                        <div class="m-combo-action m-select-department">
                                                            <div class="m-btn-dropdown">
                                                                <div class="m-icon-16 m-icon-arrow-dropdown">
                                                                </div>
                                                            </div>
                                                        </div>
                                                    </div>
                                                    <!-- API lấy thông tin phòng ban -->
                                                    <TheListDepartment apiDepartments="https://amis.manhnv.net/api/v1/Departments"></TheListDepartment>         
                                                </div>
                                                <div class="m-input-message-error">&lt;Đơn vị&gt;không được để trống</div>
                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Chức danh"></TheLable>
                                                </div>
                                                <input type="text" class="m-input" name="EmployeePosition"
                                                    maxlength="128" propName="EmployeePosition" tabindex="10" />
                                            </div>
                                        </div>
                                        <div class="m-col-2 m-flex-wrap">
                                            <div class="m-input-40 m-pr-6 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Ngày sinh"></TheLable>
                                                </div>
                                                <input type="date" class="m-input" name="DateOfBirth"
                                                    propName="DateOfBirth" tabindex="3" />
                                            </div>
                                            <div class="m-input-60 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Giới tính"></TheLable>
                                                </div>
                                                <div class="m-radio-group">
                                                    <label class="m-con-radio">
                                                        <input type="radio" class="m-input-radio" value="0"
                                                            name="Gender" checked tabindex="4" />
                                                        <span class="m-radio">
                                                            <span class="m-radio-border"></span>
                                                            <span class="m-radio-circle"></span>
                                                        </span>
                                                        <span class="m-radio-label">Nam</span>
                                                    </label>
                                                    <label class="m-con-radio">
                                                        <input type="radio" class="m-input-radio" value="1"
                                                            name="Gender" tabindex="5" />
                                                        <span class="m-radio">
                                                            <span class="m-radio-border"></span>
                                                            <span class="m-radio-circle"></span>
                                                        </span>
                                                        <span class="m-radio-label">Nữ</span>
                                                    </label>
                                                    <label class="m-con-radio">
                                                        <input type="radio" class="m-input-radio" value="2"
                                                            name="Gender" tabindex="6" />
                                                        <span class="m-radio">
                                                            <span class="m-radio-border"></span>
                                                            <span class="m-radio-circle"></span>
                                                        </span>
                                                        <span class="m-radio-label">Khác</span>
                                                    </label>
                                                </div>
                                            </div>
                                            <div class="m-input-60 m-pr-6 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <div class="m-input-title" title="Số chứng minh nhân dân">Số CMND
                                                    </div>
                                                </div>
                                                <input type="text" class="m-input" name="IdentityNumber" maxlength="20"
                                                    propName="IdentityNumber" tabindex="8" />
                                            </div>
                                            <div class="m-input-40 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Ngày cấp"></TheLable>
                                                </div>
                                                <input type="date" class="m-input" name="IdentityDate"
                                                    propName="IdentityDate" tabindex="9" />
                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Nơi cấp"></TheLable>
                                                </div>
                                                <input type="text" class="m-input" name="IdentityPlace"
                                                    propName="IdentityPlace" tabindex="11" />
                                            </div>
                                        </div>
                                    </div>
                                    <div class="m-content-1-col m-pb-24">
                                        <div class="m-input-100">
                                            <div class="m-flex-wrap">
                                                <TheLable lable="Đại chỉ"></TheLable>
                                            </div>
                                            <input type="text" class="m-input" name="Address" propName="Address"
                                                tabindex="12" />
                                        </div>
                                    </div>
                                    <div class="m-content-4-col">
                                        <div class="m-col-1 m-pr-6">
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <div class="m-input-title" title="Điện thọai di động">ĐT
                                                        di động</div>
                                                </div>
                                                <input type="text" class="m-input" name="TelephoneNumber"
                                                    propName="TelephoneNumber" tabindex="13" />
                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Tài khoản ngân hàng"></TheLable>
                                                </div>
                                                <input type="text" class="m-input" name="BankAccountNumber"
                                                    propName="BankAccountNumber" tabindex="16" />
                                            </div>
                                        </div>
                                        <div class="m-col-2 m-pr-6">
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <div class="m-input-title" title="Điện thoại cố định">ĐT
                                                        cố định</div>
                                                </div>
                                                <input type="text" class="m-input" name="PhoneNumber"
                                                    propName="PhoneNumber" tabindex="14" />
                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Tên ngân hàng"></TheLable>

                                                </div>
                                                <input type="text" class="m-input" name="BankName" propName="BankName" tabindex="17" />
                                            </div>
                                        </div>
                                        <div class="m-col-3 m-pr-6">
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Email"></TheLable>
                                                </div>
                                                <input type="text" id="m-email" class="m-input" name="Email" propName="Email" tabindex="15" isEmail />
                                                <div class="m-input-message-error">&lt;Email&gt;Chưa đúng định dạng</div>

                                            </div>
                                            <div class="m-input-100 m-pb-24">
                                                <div class="m-flex-wrap">
                                                    <TheLable lable="Chi nhánh"></TheLable>
                                                </div>
                                                <input type="text" class="m-input" name="BankBranchName" propName="BankBranchName" tabindex="18" />
                                            </div>
                                        </div>
                                    </div>
                                </form>
                            </div>
                            <div class="m-popup--footer">
                                <div class="m-divine"></div>
                                <div class="m-popup-btn">
                                    <div class="m-popup-btn-left">
                                        <button
                                            class="m-button m-button-secondary m-button-size-default m-button-border-false m-button-close "
                                            tabindex="21" id="m-button-close ">
                                            <div class="m-button-text">Hủy</div>
                                        </button>
                                    </div>
                                    <div class="m-popup-btn-right">
                                        <button
                                            class="m-button m-button-secondary m-button-size-default m-button-border-false m-popup-store-btn"
                                            tabindex="20">
                                            <div class="m-button-text">Cất</div>
                                        </button>
                                        <button
                                            class="m-button m-button-size-default m-button-border-false m-popup-store-and-add-btn"
                                            tabindex="19">
                                            <div class="m-button-text">Cất và thêm</div>
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import TheListDepartment from "./TheListDepartment.vue";
import TheLable from "../base/Lable.vue"
import TheCheckbox from "../base/Checkbox.vue"
// import TheButton from "../base/Button.vue"
export default {
    name : "ThePopup",
    props : ["showFormEmployee"],
    components:{
       TheListDepartment, TheLable, TheCheckbox, 
    },
    methods: {
        hiddenFormEmployee(){
            this.isShow=!this.isShow
        }
  },
    data(){
       return {
            isShow : true,
       }
    }
}
</script>
<style scoped>

</style>