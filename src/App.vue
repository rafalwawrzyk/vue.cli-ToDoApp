<template>
   <div>
        <displayTodo-app :todos="todos"></displayTodo-app>
        <filterTodos-app :todos="todos"></filterTodos-app>
   </div>
</template>
<script>

    import DisplayTodos from './components/displayTodos.vue'
    import FilterTodos from './components/filterTodos.vue'

    export default {
        components: {

            'displayTodo-app': DisplayTodos,
            'filterTodos-app': FilterTodos

        },
        data() {
            return {
                title: "ToDo App",
                show: true,
                visibility: 'all',
                hide: false,
                todos: [{
                        name: 'first task',
                        complete: false,
                    },
                    {
                        name: 'second',
                        complete: false
                    }
                ],

                complete: 'complete'
            }
        },

        watch: {
            todos: {
                //set todos to local storage
                handler: function() {
                    localStorage.setItem('todos', JSON.stringify(this.todos))
                },
                deep: true

            }
        },
        mounted: function() {
            //get todos form localStorage
            //and set todos to json todos
            if (localStorage.getItem('todos')) {
                this.todos = JSON.parse(localStorage.getItem('todos'));
            }
        },
        beforeMount: function() {
            let fullpage = document.querySelector('.fullpage-animate');
            fullpage.classList.add('hideAnimate')
        },
    }
</script>
<style>


</style>
