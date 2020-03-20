<template>
  <h3>
      {{ title }}
      <button @click="$emit('deleteTask')">Eliminar</button>
    </h3>
</template>

<script>
export default {
    name: 'Task',
    props: {
        title: String
    }
}
</script>

<style>

</style>