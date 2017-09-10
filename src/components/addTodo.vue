<template>
       <div class="inputContainer">
            <div class="addBox">
                <input type="text" placeholder="add todo..." @keyup.enter="addTodo">
                <button @click="addTodo" class="addBtn">✚</button>
            </div>

        </div>
</template>

<script>
    export default {
        props: ["todos"],
        data() {
            return {

            }
        },
        methods: {
            addTodo: function() {
                let input = document.querySelector('.addBox input');
                if (input.value != "") {
                    this.todos.push({
                        name: input.value,
                        complete: false,
                    })
                    input.value = "";
                }
            },
            consoleme: function() {
                console.log(this.todos)
            }
        }
    }

</script>
