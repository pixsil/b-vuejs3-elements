<template>
    <div class="progress custom-mt">
        <div role="progressbar" class="progress-bar bg-primary" :class="[variant !== null ? 'bg-'+ variant : '']" :style="widthStyle">
            <template v-if="$attrs.hasOwnProperty('show-value')">
                {{ widthLabel }}
            </template>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        value: Number,
        variant: String,
        max: Number,
    },

    components: {},

    data() {
        return {}
    },

    methods: {
    },

    mounted() {
    },

    created() {
    },


    computed: {
        widthLabel() {
            return Math.round(this.value);
        },
        widthStyle() {
            let width = 100 / this.max * this.value;

            width = Math.round(width);

            return `width: ${width}%`;
        }
    }
}
</script>

<style scoped>
.progress {
    background-color: #e9ecef;
    border-radius: .25rem;
    font-size: .675rem;
    height: 1rem;
    line-height: 0
}

.progress,.progress-bar {
    display: flex;
    overflow: hidden
}

.progress-bar {
    background-color: #078e1d;
    color: #fff;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    transition: width .6s ease;
    white-space: nowrap
}

@media (prefers-reduced-motion:reduce) {
    .progress-bar {
        transition: none
    }
}

.progress-bar-striped {
    background-image: linear-gradient(45deg,hsla(0,0%,100%,.15) 25%,transparent 0,transparent 50%,hsla(0,0%,100%,.15) 0,hsla(0,0%,100%,.15) 75%,transparent 0,transparent);
    background-size: 1rem 1rem
}

.progress-bar-animated {
    -webkit-animation: progress-bar-stripes 1s linear infinite;
    animation: progress-bar-stripes 1s linear infinite
}

@media (prefers-reduced-motion:reduce) {
    .progress-bar-animated {
        -webkit-animation: none;
        animation: none
    }
}
</style>
