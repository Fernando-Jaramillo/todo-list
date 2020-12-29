<template>
    <div>
        <TodoCo/>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from "vue-property-decorator";
    import TodoCo from "../components/TodoCo.vue";
    
    @Component({
        components:{
            TodoCo,
        },
    })
    export default class Todo extends Vue{
    }
</script>
 