<template>
    <div class="card">
        <div v-if="$slots.header" class="card-header">
            <slot name="header"></slot>
        </div>
        <template v-if="$attrs.hasOwnProperty('no-body')">
            <slot></slot>
        </template>
        <template v-else>
            <b-card-body>
                <slot></slot>
            </b-card-body>
        </template>
    </div>
</template>

<script>
export default {
    props: {
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
