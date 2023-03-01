<script>
export default {
    props: {
        name: String, 
        salary: Number, 
        age: Number
    },
    data() {
        return {
        }
    }
}
</script>

<template>
<p>{{ name }} 
<br>
{{ salary }} 
<br>
{{ age }}</p>
</template>
<style>
</style>