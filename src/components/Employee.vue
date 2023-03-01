<script>
export default {
    props: ['name', 'surn', 'age'],
    data() {
        return {
        }
    }
}
</script>

<template>
   <p class="developer">{{ name }}</p>
   <p class="developer">{{ surn }}</p>
   <p class="developer">{{ age }}</p>
</template>

<style>
</style>