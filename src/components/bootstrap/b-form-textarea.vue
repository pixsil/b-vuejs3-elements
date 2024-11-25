<template>
    <textarea :value="modelValue"
              @input="resizeTextarea"
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
    },

    components: {},

    data() {
        return {}
    },

    methods: {
        resizeTextarea(event) {
            const textarea = event.target;
            textarea.style.height = 'auto'; // Reset the height
            textarea.style.height = `${textarea.scrollHeight}px`; // Adjust to fit content
            this.$emit('update:modelValue', textarea.value); // Update modelValue
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
textarea {
    transition: height 0.2s ease; /* Optional: smooth height adjustment */
}
</style>