<template>
    <div class="select" @mouseleave="closeOptions">
        <div class="select-title">
            <span class="select-title-text">{{ title }}</span>
            <span v-if="required" class="select-title-required">*</span>
        </div>
        <div class="select-wrapper" @click="toggleOption">
            <div :class="[showOptions ? 'skiped-bottom ' : 'select-wrapper-field']" 
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
</style>