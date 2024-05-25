<template>
    <div>
        <button class="button" :type="type">
            {{ title }}
        </button>
    </div>
</template>

<script>
    export default {
        props: {
            type: { type: String, default: "button" },
            title: { type: String, default: "Title button" },
        }
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.button {
    @include flex-row(center, center);
    @include font;
    font-size: 12px;
    height: 38px;
    white-space: nowrap;
    padding: 0px 10px;
    padding-top: 2px;
    margin: 0px 10px;
    border: $min-border;
    border-radius: $min-radius;
    color: $text-input-color;
    background-color: $backdrop-color;
    cursor: pointer;

    &:active {
        border: $main-border-focus;
        background-color: $backdrop-label-color;
    }
}
</style>