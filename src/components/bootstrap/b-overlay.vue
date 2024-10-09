<template>
    <div class="b-overlay position-absolute" style="inset: 0px; z-index: 10;"><div class="position-absolute bg-light rounded-sm" style="inset: 0px; opacity: 0.85; backdrop-filter: blur(2px);"></div><div class="position-absolute" style="top: 50%; left: 50%; transform: translateX(-50%) translateY(-50%);"><span aria-hidden="true" class="spinner-border"><!----></span></div></div>
</template>

<script>
export default {
    props: {
        show: Boolean,
        rounded: String
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
        // Event.('event', () => {});
    },


    computed: {
        // func() {}
    }
}
</script>

<style scoped>
</style>
