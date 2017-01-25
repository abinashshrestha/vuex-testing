<template>
    <div id="current-todos" class="container">
        <h3 v-if="todos.length > 0">Current({{ todos.length }})</h3>

        <ul class="list-group">
            <li class="list-group-item" v-for="todo in todos">
                {{ todo.body }}
                <div class="btn-group">
                    <button class="btn btn-default btn-sm" @click="edit(todo)"><span class="glyphicon glyphicon-edit"></span> Edit</button>
                    <button class="btn btn-default btn-sm" @click="complete(todo)"><span class="glyphicon glyphicon-ok-circle"></span> Complete</button>
                    <button class="btn btn-default btn-sm" @click="remove(todo)"><span class="glyphicon glyphicon-remove-circle"></span> Remove</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default{
        methods: {
            edit(todo){
                console.log(todo);

                this.$store.dispatch('editTodo', todo)
            },
            complete(todo){
                this.$store.dispatch('completeTodo', todo)
            },
            remove(todo){
                this.$store.dispatch('removeTodo', todo)
            }
        },
        computed: {
            todos(){
                return this.$store.getters.todos
            }
        }
    }
</script>

<style>
    .btn-group{
        float: right;
    }
</style>