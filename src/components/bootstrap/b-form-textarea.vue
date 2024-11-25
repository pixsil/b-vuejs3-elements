<template>
    <textarea :value="modelValue"
              @input="onChange"
              ref="textarea"
              id="textarea"
              wrap="soft"
              class="form-control"
              style="resize: none; overflow-y: hidden;">
    </textarea>
</template>

<script>
export default {
    props: {
        modelValue: String,
        noAutoShrink: {
            type: Boolean,
            default: false,
        },
    },

    data() {
        return {
            max_height: null,
        };
    },

    methods: {
        onChange(event) {
            const textarea = event.target;

            this.resizeTextarea(textarea);

            this.$emit('update:modelValue', textarea.value);
        },
        resizeTextarea(textarea)
        {
            // Reset for calculation
            textarea.style.height = 'auto';
            const new_height = textarea.scrollHeight;

            if (!this.max_height) {
                this.max_height = new_height;
            }

            if (this.max_height < new_height) {
                this.max_height = new_height;
            }

            if (this.noAutoShrink) {
                textarea.style.height = `${this.max_height}px`;
            } else {
                textarea.style.height = `${new_height}px`;
            }
        },
    },

    mounted() {
        this.$nextTick(() => {
            // Initialize the textarea size on mount
            this.resizeTextarea(this.$refs.textarea);
        });
    },
};
</script>

<style scoped>
</style>
