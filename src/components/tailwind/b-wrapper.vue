<template>
    <template v-if="tag && show">
        <component :is="tag">
            <slot></slot>
        </component>
    </template>
    <template v-else>
        <slot></slot>
    </template>
</template>

<script>
export default {
    props: {
        tag: {
            default: null,
            type: String,
        },
        show: {
            default: true,
            type: Boolean,
        },
    },

    components: {},

    data() {
        return {
        }
    },

    methods: {
    },

    mounted() {
    },

    created() {
        // Event.('event', () => {});
    },


    computed: {
        // func() {}
    }
}
</script>

<style scoped>
</style>
