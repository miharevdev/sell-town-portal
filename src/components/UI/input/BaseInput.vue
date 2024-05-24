<template>
    <div class="input">
        <div class="input-title">
            <span v-if="!hasLeftTitile" class="input-title-text">{{ title }}</span>
            <span v-if="!hasLeftTitile && title!== '' && required" class="input-title-required">*</span>
        </div>
        <div class="input-wrapper">
            <div class="" :class="[hasLeftTitile ? 'left-title' : 'input-title']">
                <span v-if="hasLeftTitile" class="input-title-text">{{ title }}</span>
                <span v-if="hasLeftTitile && title!== '' && required" class="input-title-required">*</span>
            </div>
            <input class="input-wrapper-field" :class="[hasLeftTitile ? 'skiped-left' : '']" :type="type" :placeholder="placeholder">
        </div>
        <div class="input-error">
            <span class="input-error-message">
                {{ errorMessage }}
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            type: { type: String, default: "text" },
            placeholder: { type: String, default: "" },
            title: { type: String, default: "" },
            hasLeftTitile: { type: Boolean, default: false },
            errorMessage: { type: String, default: "" },
            required: { type: Boolean, default: false },
        },
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.left-title {
    @include flex-row(center, center);
    height: 36px;
    white-space: nowrap;
    padding-left: 10px;
    padding-right:10px;
    border: $min-border;
    border-radius: $min-radius;
    border-top-right-radius: 0px;
    border-bottom-right-radius: 0px;
    border-right: none;
    background-color: $backdrop-label-color;
}

.skiped-left {
    border-top-left-radius: 0px !important;
    border-bottom-left-radius: 0px !important
}

.input {
    @include flex-col(flex-start, flex-start);
    @include font;
    margin: 5px;
    padding: 10px;

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

        &-left-title {
            font-size: 12px;
            color: $text-color;
            border: $min-border;
            border-radius: $min-radius;
        }

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
}
</style>