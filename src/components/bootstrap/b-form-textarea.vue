<template>
    <textarea :value="modelValue"
              @input="resizeTextarea"
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
        resizeTextarea(event) {
            const textarea = event.target;

            // reset for calculation
            textarea.style.height = 'auto';
            let new_height = textarea.scrollHeight;

            if (this.max_height < new_height) {
                this.max_height = textarea.scrollHeight;
            }

            if (this.noAutoShrink) {
                textarea.style.height = `${this.max_height}px`;
            } else {
                textarea.style.height = `${new_height}px`;
            }

            this.$emit('update:modelValue', textarea.value);
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
</style>