<template>
    <template v-if="href !== null">
        <a :href="href" class="btn" :class="[ this.$attrs['class'], variant !== null ? 'btn-'+ variant : '',  size !== null ? 'btn-'+ size: '']" target="_self"><slot></slot></a>
    </template>
    <template v-else>
        <button type="button" class="btn" :class="[ this.$attrs['class'], variant !== null ? 'btn-'+ variant : '',  size !== null ? 'btn-'+ size: '']"><slot></slot></button>
    </template>
</template>

<script>
export default {
    props: {
        href: {
            type: String,
            default: null,
        },
        variant: {
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
