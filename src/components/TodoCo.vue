<template>
    <div>
        <FormTodo 
            @addTodo="addTodo($event)"
            @deleteTodos="deleteTodoS($event)"
        />
        <table class="table">
            <thead>
                <tr>
                    <th>Index</th>
                    <th>To do</th>
                    <th>Delete</th>
                </tr>
            </thead>
            <tbody v-if="todos.length > 0">
                <TodoItem v-for="(todo, index) in todos" v-bind:key="index" @deleteTodo="deleteTodo(index)" :index="index" :todo="todo"/>
            </tbody>
            <tbody v-else>
                <tr>
                    <td colspan="3">There are no to do</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";
    import FormTodo from "./FormTodo.vue";
    import TodoItem from "./TodoItem.vue";


    @Component ({
        components:{
            FormTodo,
            TodoItem
        }
    })
    export default class TodoCo extends Vue {
        todos: any =  [];

        addTodo(todo: String): void {
            this.todos.push(todo);
        }

        deleteTodo(index: Number): void{
            this.todos.splice(index, 1);

        }
        deleteTodoS(): void{
            this.todos = [];
        }
  }

</script>
