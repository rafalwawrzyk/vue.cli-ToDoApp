<template>
       <div class="filterBox">
            <button @click="completed"><i class="fa fa-check-square-o" aria-hidden="true"></i></button>
            <button @click="all"><i class="fa fa-list" aria-hidden="true"></i></button>
            <button @click="uncompleted"><i class="fa fa-tasks" aria-hidden="true"></i>
        </button>
        </div>
</template>

<script>
    export default {
        props: ['todos'],
        data() {
            return {

            }
        },
        methods:{
               completed: function () {
            let list = document.querySelectorAll('p')
            for (let i = 0; i < list.length; i++) {
                if (list[i].className !== "taskDone") {
                    list[i].parentElement.style.display = "none"
                } else {
                    list[i].parentElement.style.display = "block"
                }
            }
        },
              uncompleted: function () {
            let list = document.querySelectorAll('p')
            for (let i = 0; i < list.length; i++) {
                if (list[i].className == "taskDone") {
                    list[i].parentElement.style.display = "none"
                } else {
                    list[i].parentElement.style.display = "block"
                }
            }
        },
                    all: function () {
            let list = document.querySelectorAll('p');
            for (let i = 0; i < list.length; i++) {
                list[i].parentElement.style.display = "block"
            }
        },
        }
       
    }

</script>
