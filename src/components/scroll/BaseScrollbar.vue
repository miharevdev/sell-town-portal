<template>
    <div class="scroll">
        <slot />
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
@import "~/src/assets/styles/custom.scss";

.scroll {
    @include flex-col(flex-start, center);
    height: 100%;
    width: 100%;
    overflow: scroll;
}

::-webkit-scrollbar {
    height: 6px;
    width: 6px;
    border-radius: $min-radius;
    padding-inline: 4px;
    background-color: #f3f4f6;
}

::-webkit-scrollbar-corner {
    background-color: #e5e7eb;
}

::-webkit-scrollbar-thumb {
    background-color: #d1d3d6;
    border-radius: $min-radius;

    &:hover {
        background-color: #9ca3af;
    }
}

</style>