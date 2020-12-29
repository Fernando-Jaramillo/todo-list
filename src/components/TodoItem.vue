<template>
   <tr>
        <td>{{ index + 1 }}</td>
        <td>{{ todo }}</td>
        <td> <button v-on:click="$emit('deleteTodo')" class="btn btn-danger btn-block">Delete</button> </td>
    </tr>
</template>

<script lang="ts">

import {Component, Prop, Vue} from "vue-property-decorator";

@Component
export default class TodoItem extends Vue {
    @Prop() index!: Number;
    @Prop() todo!: String;
}

</script>