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
</style>