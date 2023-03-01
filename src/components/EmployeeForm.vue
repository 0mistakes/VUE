<script>
export default {
    data() {
        return {
            newName: ' ',
            newSurn: ' ',
        }
    },
    methods: {
        save(){
            this.$emit('add', this.newName, this.newSurn)
        }
    }
}
</script>

<template>
    <input class="button" v-model="newName">
    <br>
    <br>
    <input class="button" v-model="newSurn">
    <br>
    <button class="button" @click="save">save</button>
</template>