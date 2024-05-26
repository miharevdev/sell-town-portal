<template>
    <div class="table-wrapper">
        <div class="table">
            <div v-if="control" class="table-control">

            </div>
            <base-scrollbar>
                <div class="table-header">
                    <div v-for="(field, i) in fields" :key="i" class="table-header-item" :style="`min-width: ${field.width}px`">
                        <span class="table-header-item-text">{{ field.cap }}</span>
                    </div>
                </div>
                <div class="table-body">
                    <div v-for="(tData, i) in tableData" :key="i" class="table-body-line">
                        <span v-for="(td, i) in tData" :key="i" class="table-body-line-item" :style="`min-width: ${td.width}px`">
                            {{ td.value}}
                        </span>
                        <slot v-for="(slot, i) in slots" :key="i" class="slot" :name="slot" />
                    </div>
                </div>
            </base-scrollbar>
        </div>
    </div>
</template>

<script>
import BaseScrollbar from "../scroll/BaseScrollbar.vue"

    export default {
        components: {
            BaseScrollbar,
        },

        props: {
            control: { type: Boolean, default: false },
            fields: { type: Array, default: () => { return [] } },
            tableData: { type: Array, default: () => { return [] } },
            slots: { type: Array, default: () => { return [] } },
        },

        data() {
            return {

            }
        },

        mounted() {
            this.tableData.forEach(td => {
                for (let key in td) {
                    this.fields.forEach(f => {
                        if (key === f.key) {
                            td[key] = { value: td[key], width: f.width }
                        }
                    })
                }
            })
        }
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.slot {
    @include flex-col(flex-start, center);
    height: 100%;
    width: 200px;
    background-color: #fff;
}

.table-wrapper {
    @include flex-col(flex-start, center);
    height: 100%;
    width: 100%;
}

.table {
    @include flex-col(flex-start, center);
    height: calc(100% - 32px);
    width: calc(100% - 32px);
    margin: auto;
    border: $min-border;
    border-radius: $min-radius;

    &-control {
        @include flex-row(flex-start, center);
        min-height: 50px;
        width: 100%;
        padding-top: 8px;
        border-bottom: $min-border;
    }

    &-header {
        @include flex-row(flex-start, center);
        min-height: 50px;
        width: 100%;
        border-bottom: $min-border;
        
        &-item {
            @include flex-row(flex-start, center);
            height: 100%;
            border-bottom: $min-border;
            padding-inline: 20px;
            margin-bottom: -1px;

            &-text {
                @include font;
                font-size: 12px;
                color: $text-input-color;
            }
        }
    }

    &-body {
        @include flex-col(flex-start, center);
        height: 100%;
        width: 100%;

        &-line {
            @include flex-row(flex-start, center);
            min-height: 50px;
            width: 100%;

            &-item {
                @include flex-row(flex-start, center);
                @include font;
                font-size: 12px;
                color: $text-input-color;
                padding-inline: 20px;
            }
        }
    }
}
</style>