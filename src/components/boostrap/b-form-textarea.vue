<template>
    <textarea :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" id="textarea" wrap="soft" class="form-control" style="resize: none; overflow-y: scroll; height: 84px;"></textarea>
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
</style>
