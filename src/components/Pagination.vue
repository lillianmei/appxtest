<script setup lang="ts">
import { ref } from 'vue'

const selectValue = ref(1)

const options = [
    {
        value: 1,
        label: 1
    },
    {
        value: 2,
        label: 2
    },
    {
        value: 3,
        label: 3
    }
]

const prevPage = () => {
    if (selectValue.value === 1) return
    selectValue.value -= 1
}
const nextPage = () => {
    if (selectValue.value === options.length) return
    selectValue.value += 1
}
</script>

<template>
    <div class="pagination">
        <h1>My Collection</h1>
        <div class="pagination__select">
            <div>Total 480 |</div>
            <div class="pagination__select-page">
                <div class="pagination-btn prev" @click="prevPage"></div>
                <el-select v-model="selectValue" class="m-2 page-select" placeholder="Select" size="large">
                    <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
                </el-select>
                <div class="pagination-btn next" @click="nextPage"></div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.pagination {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 16px 16px 0;

    &__select {
        display: flex;
        align-items: center;
        div{
            color: #737791;

        }
    }

    &__select-page {
        display: flex;
        align-items: center;
        margin-left: 12px;

        .el-select {
            width: 48px;
            margin:0 8px;

            .el-input {
                --el-input-border-color: #ebebeb;
            }
        }
        .el-input--large .el-input__wrapper{
            padding: 1px 9px;
        }

        .pagination-btn {
            width: 8px;
            height: 12px;
            background-size: contain;
            background-repeat: no-repeat;

            &.prev {
                background-image: url('@/assets/image/prev-btn.svg');
            }

            &.next {
                background-image: url('@/assets/image/next-btn.svg');
            }
        }
    }
}
</style>
