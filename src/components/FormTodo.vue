<template>
    <div>
        <form @submit.prevent="newTodo">
                <div class="form-group">
                    <label for="todo">Add a to do</label>
                    <input type="text" autocomplete="off" class="form-control" id="todo" v-model="todo">
                </div>
                <button type="submit" class="btn btn-primary btn-block">Add a to do</button>
        </form>
        <button v-on:click="deleteAll" class="btn btn-dark btn-block">Delete all</button>
    </div>
</template>
<script lang="ts">
import {Component, Vue} from "vue-property-decorator";

@Component
export default class FormTodo extends Vue {
    todo: String = "";
    newTodo(): void{
        this.$emit('addTodo', this.todo);
        this.todo = "";
    }
    deleteAll(): void{
        this.$emit("deleteTodos")
    }
}


</script>