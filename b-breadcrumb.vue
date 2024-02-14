<template>
    <ol class="breadcrumb">
        <template v-for="(item, index) in items" class="breadcrumb-item">
            <li v-if="items.length !== index + 1" class="breadcrumb-item">
                <a :href="item.href" target="_self" class="">{{ item.text }}</a>
            </li>
            <li v-else class="breadcrumb-item active">
                <span aria-current="location">{{ item.text }}</span>
            </li>
        </template>
    </ol>
</template>

<script>
export default {
    props: {
        items: Array,
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
