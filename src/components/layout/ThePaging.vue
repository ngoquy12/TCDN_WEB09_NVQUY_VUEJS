<template>
    <div>
        <div class="m-pagination">
            <div class="m-pagination-left">
                <div class="m-total-record">Tổng số: <b class="m-total">100</b> bản ghi</div>
            </div>
            <div class="m-pagination-right">
                <div class="m-record-in-page">
                    <div class="m-combo-box">
                        <div class="m-combo-main-content">
                            <div class="m-selected-options">
                                <input type="text" class="m-combo-input" readonly="true" autofocus="autofocus"
                                    value="10 bản ghi trên 1 trang" />
                            </div>
                            <div class="m-combo-action m-select-record">
                                <div class="m-btn-dropdown">
                                    <div class="m-icon-16 m-icon-arrow-dropdown m-dropdown-close">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                     <!-- Combo dropdown chọn số bản ghi -->
                     <div class="m-combo-dropdown-panel">
                        <div class="m-dropdown-body-container">
                            <ul class="m-combo-dropdown-items">
                                <li class="m-combo-box-item m-item-highlight" data-total="10">10 bản ghi trên 1 trang</li>
                                <li class="m-combo-box-item" data-total="20">20 bản ghi trên 1 trang</li>
                                <li class="m-combo-box-item" data-total="30">30 bản ghi trên 1 trang</li>
                                <li class="m-combo-box-item" data-total="50">50 bản ghi trên 1 trang</li>
                                <li class="m-combo-box-item" data-total="100">100 bản ghi trên 1 trang</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="m-page-number">
                    <div class="m-prev-page">Trước</div>
                    <div class="m-page-index">1</div>
                    <div class="m-page-index">2</div>
                    <div class="m-page-index">3</div>
                    <div class="m-next-page">Sau</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    name: "ThePaging",
    props: [],
    methods: {

    },
    data() {

    }
};
</script>
<style scoped>

</style>