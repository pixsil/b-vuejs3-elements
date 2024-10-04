<template>

    <select :disabled="disabled"
            :required="required"
            class="custom-select"
            :class="[ size !== null ? 'input-'+ size: '', 'custom-select-'+ size]"
            style="min-width: 200px;"
            :value="modelValue"
            @change="onChange"
        >
            <slot name="first"></slot>

            <template v-if="isObject(options)">
                <template v-for="(option, key) in options">

                    <template v-if="isObject(option)">
                        <option :value="option[valueField] ?? ''">{{ option[textField] }}</option>
                    </template>
                    <template v-else>
                        <option :value="key ?? ''">{{option }}</option>
                    </template>

                </template>
            </template>
            <template v-else>
                <template v-for="(option) in options">
                    <template v-if="isObject(option)">
                        <option :value="option[valueField] ?? ''">{{ option[textField] }}</option>
                    </template>
                    <template v-else>
                        <option :value="option">{{ option }}</option>
                    </template>

                </template>
            </template>

            <slot></slot>
    </select>
</template>

<script>

export default {

    props: {
        modelValue: null,
        size: {
            default: 'md',
            type: String,
        },
        options: [Array, Object],
        disabled: {
            type: Boolean,
            default: null,
        },
        required: {
            type: Boolean,
            default: null,
        },
        textField: {
            type: String,
            default: 'text'
        },
        valueField: {
            type: String,
            default: 'value'
        }
    },

    emits: [
        'update:modelValue',
    ],

    components: {},

    data() {
        return {}
    },

    methods: {
        isObject(objValue) {
            return objValue && typeof objValue === 'object' && objValue.constructor === Object;
        },
        onChange(event) {
            this.$emit('update:modelValue', event.target.value)
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
