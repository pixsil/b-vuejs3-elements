<template>
    <div role="group" class="form-row form-group">
        <label :for="[ labelFor !== null ? labelFor : '' ]" class="col-form-label" :class="[ labelColsMd !== null ? 'col-md-'+ labelColsMd : '', labelColsLg !== null ? 'col-lg-'+ labelColsLg : '' ]">{{ label }}</label>
        <div class="col">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        label: String,
        labelColsMd: {
            type: [Number, String],
            default: null,
        },
        labelColsLg: {
            type: [Number, String],
            default: null,
        },
        labelFor: {
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
        // Event.('event', () => {});
    },


    computed: {
        // func() {}
    }
}
</script>

<style scoped>
</style>
