<!-- converted -->
<template>
    <ol class="breadcrumb">
        <template v-for="(item, index) in items" :key="index">
            <li :class="{ 'breadcrumb-item': true, 'active': items.length === index + 1 }">
                <a v-if="items.length !== index + 1" :href="item.href" target="_self">{{ item.text }}</a>
                <span v-else aria-current="location">{{ item.text }}</span>
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
