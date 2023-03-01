
<script>
export default {
    emits: ['show', 'show1'],
    data() {
        return {
        }
    },
    methods: {
        handleName() {
            this.$emit('show', 'Karina Volkova');
        },
        handleSalary(){
            this.$emit('show1', 'Leha Boroda', '18500');
        }
    }
}
</script>

<template>
<button class="button" @click="handleName">Имя</button>
<button class="button" @click="handleSalary">Зарплата</button>
</template>
<style>
</style>