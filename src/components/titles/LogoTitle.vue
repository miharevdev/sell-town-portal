<template>
    <div class="logo-title">
        <span class="logo-title-text" :style="`font-size:${textSize()}px`">{{ title }}</span>
    </div>
</template>

<script>
    export default {
        props: {
            title: { type: String, default: "" },
            size: { type: String, default: "md" }
        },

        methods: {
            textSize() {
                if (this.size === "sm") {
                    return "16"
                } else if (this.size === "md") {
                    return "22"
                } else if (this.size === "xl") {
                    return "28"
                }
            }
        }
    }
</script>
