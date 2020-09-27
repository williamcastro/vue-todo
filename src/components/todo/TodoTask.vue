<template>
    <div class="task" :class="{ active: active === true }" @click="$emit('setActive', task)">
        <span>{{ task.title }}</span>
    </div>
</template>

<script>
    export default {
        name: "TodoTask",
        props: {
            task: {
                type: Object,
            },
            active: {
                type: Boolean,
                default: false,
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../../assets/sass/mixins";

    .task {
        display: flex;
        justify-content: space-between;
        font-size: 14px;
        margin: 15px 0;
        padding: 15px;
        background: #fff;
        border-radius: 5px;
        transition: 0.1s;
        @include animate(.2s,.1s);

        &.active {
            @include animate(.2s,.1s);
            @include scale(1.05);
            background: #fce8ff;
            box-shadow: 2px 2px 7px rgba(0,0,0,.15);
        }

        &:hover {
            @include animate(.2s,.1s);
            box-shadow: 2px 2px 5px rgba(0,0,0,.05);
            transition: 0.1s;
        }
    }
</style>
