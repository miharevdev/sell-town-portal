<template>
    <svg
        :stroke="[dark ? '#1e293b' : '#94a3b8']" 
        stroke-width="2" 
        stroke-linecap="round" 
        stroke-linejoin="round"
        viewBox="0 0 30 30"
        class="icon"
        :class="styleClasses"
    >
        <path :d="path" />
    </svg>
</template>

<script>
import icons from "@/assets/img/icons/icons.json";

export default {
    name: 'AppIcon',
    props: {
        name: String,
        size: String,
        color: String,
        hoverColor: String,
        dark: Boolean
    },
    computed: {
        path() {
            return icons[this.name];
        },
    styleClasses() {
        return [this.size, this.color].map(val => val && `is-${val}`);
    },
  },
};
</script>
<style lang="scss">
@import "~/src/assets/styles/custom.scss";

/* default */
.icon {
    width: 1.2em;
    height: 1.2em;
    fill: v-bind(color);

    &:hover {
        fill: v-bind(hoverColor);
    }
}
/* sizes */
.icon.is-menu {
    width: 2.6em;
    height: 2.6em;
}
.icon.is-large {
    width: 2em;
    height: 2em;
}
.icon.is-medium {
    width: 1.6em;
    height: 1.6em;
}
.icon.is-normal {
    width: 1.2em;
    height: 1.2em;
}
.icon.is-small {
    width: 1em;
    height: 1em;
}
.icon.is-tiny {
    width: 0.8em;
    height: 0.8em;
}
/* colors */
.icon.is-primary,
.icon.is-blue {
    fill: #2196F3
}
.icon.is-success,
.icon.is-green {
    fill: #4CAF50
}
.icon.is-danger,
.icon.is-red  {
    fill: #F44336
}
.icon.is-warning,
.icon.is-orange {
    fill: #FF9800
}
</style>