<template>
    <template v-if="$attrs.hasOwnProperty('responsive')">
        <div class="table-responsive">
            <table role="table" class="table b-table table-hover">
                <slot></slot>
            </table>
        </div>
    </template>
    <template v-else>
        <table role="table" class="table b-table table-hover">
            <slot></slot>
        </table>
    </template>
</template>

<script>
export default {
    props: {},

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
