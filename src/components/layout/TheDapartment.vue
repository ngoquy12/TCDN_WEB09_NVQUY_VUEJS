<template>
    <div>
        <div class="m-input-100 m-pb-24">
            <div class="m-flex">
                <div class="m-input-title">Đơn vị</div>
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
                <div class="m-input-message-error">&lt;Đơn vị&gt;không được để trống
                </div>
            </div>
        </div>
        <!-- Combo dropdown chọn phòng ban -->
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
                    <tr class="m-menu-items-tr">
                        <td class="m-menu-items-td" style="width: 100px; text-align: left"><span></span></td>
                        <td class="m-menu-items-td" style="width: 250px; text-align: left"><span><span></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
export default {
    name : "",
    props: [],
    methods: {
            
    },
    data(){

    }
}
</script>