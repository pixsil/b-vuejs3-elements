<template>
    <input type="text"
           :disabled="disabled"
           :value="modelValue"
           @input="$emit('update:modelValue', $event.target.value)"
           :required="required"
           class="form-control min-width-field"
           :class="[size !== null ? 'form-control-'+ size : '']"
           autocomplete="off">
</template>

<script>
export default {
    props: {
        modelValue: [String, Number],
        disabled: {
            type: Boolean,
            default: null,
        },
        required: {
            type: Boolean,
            default: null,
        },
        size: {
            type: String,
            default: null,
        },
    },

    emits: [
        'update:modelValue',
    ],

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
    }
}
</script>

<style scoped>
.min-width-field {
    min-width: 80px;
}
</style>
