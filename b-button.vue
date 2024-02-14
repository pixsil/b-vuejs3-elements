<!-- converted -->
<template>
    <template v-if="href !== null">
        <a :href="href" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :class="[ $attrs.class, size ? 'btn-' + size : '']" target="_self">
            <slot></slot>
        </a>
    </template>
    <template v-else>
        <button type="button" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :class="[ $attrs.class, size ? 'btn-' + size : '']">
            <slot></slot>
        </button>
    </template>
</template>

<script>
export default {
    props: {
        href: {
            type: String,
            default: null,
        },
        size: {
            type: String,
            default: null,
        },
    },

    components: {},

    data() {
        return {}
    },

    methods: {
        submit() {
            // this.vueForm.post('/site-feedback')
            //     .then(response => this.onSuccess())
        },
        onSuccess() {
        },
    },

    mounted() {
    },

    created() {
        console.log();
        // Event.('event', () => {});
    },


    computed: {
        // func() {}
    }
}
</script>

<style scoped>
</style>
