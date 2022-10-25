<template>
<div @dblclick="toggle(task.id)" :class="[task.reminder?'reminder':'','task']">
    <h3>{{task.text}}
    <i @click="onDelete(task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
</div>
</template>
<script>
export default {
    name:'task',
    props: {
        task:Object
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task',id)
        },
        toggle(id) {
            this.$emit('toggle-reminder',id)     
        }
        }
}
</script>