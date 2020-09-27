<template>
    <div class="column">
        <span class="column-title">{{ title }}</span>

        <div class="tasks-wrapper">
            <slot></slot>
        </div>
        <span class="column-footer">Add task...</span>
    </div>
</template>

<script>
    export default {
        name: "TodoColumn",
        props: {
            title: {
                type: String,
            }
        }
    }
</script>

<style lang="scss" scoped>
    .column {
        box-shadow: 2px 2px 5px #e1e2e3;
        padding: 15px;
        width: 20%;
        margin: 15px;
        background: #fafafa;
        border-radius: 25px;

        &-title {
            font-weight: bold;
        }

        &-footer {
            font-size: 13px;
            color: #a0a0a0;
        }

        .tasks-wrapper {
        }
    }


</style>
