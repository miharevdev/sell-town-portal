<template>
    <div class="select" @mouseleave="closeOptions">
        <div class="select-title">
            <span class="select-title-text">{{ title }}</span>
            <span v-if="required" class="select-title-required">*</span>
        </div>
        <div class="select-wrapper" @click="toggleOption">
            <div :class="[showOptions ? 'skiped-bottom' : 'select-wrapper-field']" 
                :type="type" 
                :placeholder="placeholder"
            >
            {{ value.name ? value.name : placeholder }}
            </div>
            <svg-icon
                v-if="value.name"
                class="exit" 
                name="close" 
                size="large" 
                color="#64748b" 
                hoverColor="#64748b"
                @click="clearField"
            />
        </div>
        <div v-if="showOptions" class="select-option-section">
            <div v-for="(option, i) in options" :key="i" class="select-option-section-item" @click="selected(option)">
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
import SvgIcon from "../../icon/SvgIcon.vue";

    export default {
        components: {
            SvgIcon
        },

        props: {
            options: { type: Array, default: () => { return [] } },
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
            },

            clearField() {
                this.value = {};
            }
        }
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";
</style>