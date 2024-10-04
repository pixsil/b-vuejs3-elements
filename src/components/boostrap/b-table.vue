<template>
        <b-wrapper :show="$attrs.hasOwnProperty('responsive')" tag="div" class="table-responsive">
            <table role="table" aria-busy="false" aria-colcount="5" class="table b-table table-hover">
                <thead role="rowgroup" class="">
                <tr role="row" class="">
                    <th v-for="field in local_fields" role="columnheader" scope="col" :class="field.thClass">
                        <template v-if="$slots['head('+ field.key +')']">
                            <slot :name="'head('+ field.key +')'" v-bind="{field, item}"></slot>
                        </template>
                        <template v-else>
                            <div>{{ field.label }}</div>
                        </template>
                    </th>
                </tr>
                </thead>
                <tbody role="rowgroup">
                <tr v-for="item in items" role="row" class="">
                    <td v-for="field in local_fields" :class="field.tdClass" role="cell">
<!--                        :class="checkTdClass(getPropValue(item, field.key), field.key, item)" -->
                        <template v-if="$slots['cell('+ field.key +')']">
                            <slot :name="'cell('+ field.key +')'" v-bind="{field, item}"></slot>
                        </template>
                        <template v-else>
                            {{ getPropValue(item, field.key) }}
                        </template>
                    </td>
                </tr>
                </tbody>
            </table>
        </b-wrapper>
</template>

<script>
export default {
    props: {
        items: {
            type: Array,
            default: [],
        },
        fields: {
            type: Array,
            default: null,
        },
        // tdClass: {
        //     type: [Function], // [String, Array, Function]
        //     default: null,
        // },
    },

    components: {},

    data() {
        return {
            local_fields: this.fields,
        }
    },

    methods: {
        getPropValue(sourceObject, dotNotationPath) {
            let returnData = sourceObject;

            dotNotationPath.split(".").forEach(subPath => {
                returnData = returnData[subPath] || '';
            });

            return returnData;
        },
        setFieldsByEmpty() {
            if (this.local_fields !== null) {
                return;
            }
            if (this.items.length === 0) {
                return;
            }

            // set as array
            this.local_fields = [];

            let keys = Object.keys(this.items[0]);

            keys.forEach((value) => {
                this.local_fields.push({'key': value, 'label': value})
            })
        },
        checkTdClass(value, key, item) {
            if (typeof this.tdClass === "function") {
                var td_class = this.tdClass(value, key, item)
            }

            return td_class;
        }
    },

    mounted() {
        this.setFieldsByEmpty();
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
