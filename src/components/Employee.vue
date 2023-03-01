<script>
export default {
    emits: ['show', 'show1'],
    data() {
        return {
        }
    },
    methods: {
        handle() {
            this.$emit('show');
        },
        handle1() {
            this.$emit('show1');
        },
    }
}
</script>

<template>
<button class="button" @click="handle">Prikolovni</button>
<button class="button" @click="handle1">Bebrusovi</button>
</template>
<style>
</style>