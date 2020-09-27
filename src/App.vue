<template>
    <div id="app">
        <!-- component | navbar -->
        <navbar/>

        <!-- sweepy todo -->
        <div class="sweepy-todo">
            <todo-column :title="status.title" v-for="status in columnStatus"
                         :key="status.id"
                         @getTask="getCurrentTask(status.id)">
                <todo-task v-for="task in filterStatus(status.id)"
                           @setActive="setActive"
                           :active="isActive(task)"
                           :task="task" :key="task.id"/>
            </todo-column>
        </div>

    </div>
</template>

<script>
    import Navbar from "@/components/global/Navbar";
    import TodoColumn from "@/components/todo/TodoColumn";
    import TodoTask from "@/components/todo/TodoTask";

    export default {
        name: 'App',
        components: {TodoTask, TodoColumn, Navbar},

        data() {
            return {
                columnStatus: [
                    {
                        id: 'backlog',
                        title: 'Backlog',
                    },
                    {
                        id: 'todo',
                        title: 'To Do',
                    },
                    {
                        id: 'doing',
                        title: 'Doing',
                    },
                    {
                        id: 'done',
                        title: 'Done',
                    },
                ],
                active: null,
                tasks: [
                    {
                        'id': 1,
                        'title': 'Jogar lol',
                        'status': 'backlog'
                    },
                    {
                        'id': 2,
                        'title': 'estudar vuejs',
                        'status': 'todo'
                    },
                    {
                        'id': 3,
                        'title': 'fazer freela',
                        'status': 'todo'
                    },
                    {
                        'id': 4,
                        'title': 'dormir',
                        'status': 'doing'
                    },
                    {
                        'id': 5,
                        'title': 'tomar banho',
                        'status': 'done'
                    }
                ]
            }
        },

        methods: {
            filterStatus: function (status) {
                return this.tasks.filter(
                    (task) => {
                        return task.status === status
                    })
            },

            setActive: function (task) {
                this.active = task;
            },

            isActive: function (task) {
                if (task && this.active) {
                    if (task.id === this.active.id)
                        return true;
                }

                return false;
            },

            getCurrentTask: function (statusId) {
                console.log(statusId);
                if (this.active) {
                    this.active.status = statusId;
                }
            }
        }
    }
</script>

<style lang="scss">
    @import "./assets/sass/styles.scss";

    .sweepy-todo {
        display: flex;
        justify-content: flex-start;
        margin: 15px;
        align-items: flex-start;
    }
</style>
