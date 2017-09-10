<template>
      <template>
      <div class="todoContainer">
            <ul>
                <li v-for="(todo,index) in filtered">
                    <todo-component v-bind:todo="todo">
                    </todo-component>
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


    import {eventBus} from '../main'
    export default{
        props:['userAge'],
        methods:{
            editAge:function(){
                this.userAge = 30;
//                this.$emit('ageEdited',this.userAge)
                eventBus.$emit('ageEdited',this.userAge)
            },
            
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>

</template>

<script>


    import {eventBus} from '../main'
    export default{
        props:['userAge'],
        methods:{
            editAge:function(){
                this.userAge = 30;
//                this.$emit('ageEdited',this.userAge)
                eventBus.$emit('ageEdited',this.userAge)
            },
            
        }
    }
</script>

