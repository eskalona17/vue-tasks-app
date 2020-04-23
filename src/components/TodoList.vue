<template>
    <form id="app">
        <label for="tast" class="label">tarea: </label>
        <input type="text" v-model="newTask" id="id">{{newTask}}
        <input type="submit" value="Crear tarea">
    </form>
</template>
<script>
export default {
    data: () => ({
        newTask: ''
    })
}
</script>

<style>

</style>