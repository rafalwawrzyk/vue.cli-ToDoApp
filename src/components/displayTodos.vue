<template>
    <div class="todoContainer">
                <div class="searchContainer">
            <i class="fa fa-search" aria-hidden="true" @click="hide = !hide"></i>
            <transition name="hide">
                <input v-if='hide' type="text" placeholder="search todo..." v-model="search">
            </transition>
            
            <h1>ToDo App</h1>
        </div>
           <addTodo-app :todos="todos" ></addTodo-app>
            <ul>
                <li v-for="(todo,index) in filtered">
                   <edit-app :todo="todo" :complete="complete" ></edit-app>
                    <div>
                        <button @click="removeTodo(index)"><i class="fa fa-trash" aria-hidden="true"></i></button>
                        <div class="checkBox">
                            <input type="checkbox" class="check" v-model="todo.complete" id="checked">
                        </div>
                    </div>
                </li>
            </ul>
        </div>  
</template>

<script>
    import AddToDo from './addTodo.vue';
    import EditTodo from './editTodo.vue'
    export default {
        components: {
            'addTodo-app': AddToDo,
            'edit-app': EditTodo
        },
        props: ['todos'],
        data: function() {
            return {

                hide: false,
                search: '',
                complete: ''
            }
        },

        methods: {
            onclicked: function() {
                this.edit = true;
            },
            savedTodo: function() {
                this.edit = false;
            },
            removeTodo: function(index) {
                this.todos.splice(index, 1)

            },
        },
        computed: {
            filtered: function() {
                return this.todos.filter((todo) => {
                    return todo.name.match(this.search)
                })
            }
        },
    }

</script>

<style>


</style>
