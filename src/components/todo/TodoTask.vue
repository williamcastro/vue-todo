<template>
    <div class="task">
        <span>{{ task.title }}</span>
    </div>
</template>

<script>
    export default {
        name: "TodoTask",
        props: {
            task: {
                type: Object,
            }
        }
    }
</script>

<style lang="scss" scoped>
    .task {
        display: flex;
        justify-content: space-between;
        font-size: 14px;
        margin: 15px 0;
        padding: 15px;
        background: #fff;
        border-radius: 5px;
        transition: 0.1s;

    }

    .task:hover {
        box-shadow: 2px 2px 5px #e1e2e3;
        transition: 0.1s;

    }
</style>
