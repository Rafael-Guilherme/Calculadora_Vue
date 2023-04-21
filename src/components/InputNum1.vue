<script lang="ts">
export default {
    props: {
        num1: {
            type: Number,
            required: true
        },
    },
    methods: {
        updateNum1(event: Event) {
            const target = event.target as HTMLInputElement;
            const value = Number(target.value)
            this.$emit('update:num1', value)
        },
    },
};
</script>

<template>
    <div>
        <input 
            :value="num1" 
            @input="updateNum1" 
            type="number" 
            class="input number-input">
    </div>
</template>

<style>

</style>