<script>
export default {
    props: ['name'],
    data() {
        return {
        }
    }
}
</script>

<template>
<ul class="styled">
    <li v-for="developer in name">{{ developer }}</li>
</ul>
</template>
<style>
</style>