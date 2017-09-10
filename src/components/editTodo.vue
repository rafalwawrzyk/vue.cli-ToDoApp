<template>
    <p :class="{taskDone:todo.complete}"><span @click="onclicked" v-show="!edit">{{todo.name}}</span><span v-show="edit"><input @keyup.enter="savedTodo" v-model="todo.name"  class="searchInput"/><button @click="savedTodo"><i class="fa fa-pencil" aria-hidden="true"></i></button></span> </p>
</template>

<script>
    export default {
        data() {
            return {
                edit: false
            }
        },
        props: ['todo', 'complete'],
        methods: {
            onclicked: function() {
                this.edit = true;
            },
            savedTodo: function() {
                this.edit = false;
            }
        }
    }

</script>
