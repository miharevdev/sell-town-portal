<template>
    <div class="select" @mouseleave="closeOptions">
        <div class="select-title">
            <span class="select-title-text">{{ title }}</span>
            <span v-if="required" class="select-title-required">*</span>
        </div>
        <div class="select-wrapper" @click="toggleOption">

            <div
                :class="[showOptions ? 'skiped-bottom ' : 'select-wrapper-field']" 
                :type="type" 
                :placeholder="placeholder"
            >
            {{ value.name ? value.name : placeholder }}
            </div>
        </div>
        <div v-if="showOptions" class="select-option-section">
            <div v-for="(option, i) in selectData" :key="i" class="select-option-section-item" @click="selected(option)">
                <span class="select-option-section-item-text">{{ option.name }}</span>
            </div>
        </div>
        <div class="select-error">
            <span class="select-error-message">
                {{ errorMessage }}
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            selectData: { type: Array, default: () => { return [] } },
            type: { type: String, default: "text" },
            placeholder: { type: String, default: "" },
            title: { type: String, default: "" },
            errorMessage: { type: String, default: "" },
            required: { type: Boolean, default: false },
        },

        data() {
            return {
                value: {},
                showOptions: false
            }
        },

        methods: {
            toggleOption() {
                this.showOptions = !this.showOptions;
            },

            selected(option) {
                this.value = option;
                this.showOptions = false;
            },

            closeOptions() {
                this.showOptions = false;
            }
        }
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.skiped-left {
    border-top-left-radius: 0px !important;
    border-bottom-left-radius: 0px !important
}

.skiped-bottom {
    @include flex-row(flex-start, center);
    height: 36px;
    width: 100%;
    min-width: 140px;
    margin: 2px 0px;
    padding: 0px 8px;
    border: $min-border;
    border-radius: $min-radius;
    outline: none;
    font-size: 14px;
    color: $text-input-color;
    background-color: $backdrop-color;

    &:focus {
        border: $main-border-focus;
    }
   
    border-bottom-left-radius: 0px;
    border-bottom-right-radius: 0px;
}

.select {
    @include flex-col(flex-start, flex-start);
    @include font;
    margin: 5px;
    padding: 10px;
    position: relative;

    @media screen and (min-width: 420px) {
        width: 260px;
    }

    &-title {
        @include flex-row(flex-start, center);
        height: 16px;
        color: $text-color;

        &-text {
            @include flex-row(flex-start, center);
            height: 14px;
            width: 100%;
            font-size: 10px;
            color: $text-input-color;
        }

        &-required {
            height: 14px;
            margin-left: 2px;
            margin-right: 6px;
            font-size: 11px;
            color: $error-color;
        }
    }

    &-wrapper {
        @include flex-row(flex-start, center);
        width: 100%;

        &-field {
            @include flex-row(flex-start, center);
            height: 36px;
            width: 100%;
            min-width: 140px;
            margin: 2px 0px;
            padding: 0px 8px;
            border: $min-border;
            border-radius: $min-radius;
            outline: none;
            font-size: 14px;
            color: $text-input-color;
            background-color: $backdrop-color;

            &:focus {
                border: $main-border-focus;
            }
        }
    }

    &-error {
        @include flex-row(flex-start, center);
        height: 12px;

        &-message {
            font-size: 10px;
            color: $error-color;
        }
    }

    &-option-section {
        @include flex-col(flex-start, center);
        position: absolute;
        top: 68px;
        width: calc(100% - 22px);
        border: $min-border;
        border-radius: $min-radius;
        outline: none;
        font-size: 14px;
        color: $text-input-color;
        background-color: $main-white;
        border-top-right-radius: 0px;
        border-top-left-radius: 0px;
        z-index: 1;

        &-item {
            @include flex-row(flex-start, center);
            height: 36px;
            width: 100%;

            &:first-child:hover {
                border-radius: $min-radius;
                border-top-left-radius: $min-radius;
                border-top-right-radius: $min-radius;
                border-bottom-left-radius: 0px;
                border-bottom-right-radius: 0px;
            }

            &:last-child:hover {
                border-radius: $min-radius;
                border-top-left-radius: 0px;
                border-top-right-radius: 0px;
                border-bottom-left-radius: $min-radius;
                border-bottom-right-radius: $min-radius;
            }

            &:hover {
                background-color: #f1f5f9;
            }

            &-text {
                padding: 0px 8px;
            }
        }
    }
}


</style>