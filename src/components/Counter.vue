<template>
    <h1>hola desde componente counter</h1>
    <button v-if="disabled" disabled>-</button>
    <button v-else @click="decrement">-</button>

    <span>{{ counter }}</span>
    <button @click="increment">+</button>
</template>
<script>
export default {
    data() {
        return {
            counter: 0,
            disabled: true
        }
    },
    methods: {
        increment() {
            this.counter += 1
            if (this.counter > 0) {
                this.disabled = false;
            }
        },
        decrement() {
            this.counter -= 1
            if (this.counter == 0) {
                this.disabled = true;
            }
        }
    },
    computed: {
        disabledClassComputed() {
            return this.disabled ? "disabled" : "enable";
        },
    }
}
</script>
<style scoped>
h1 {
    color: red;
}
</style>