<script lang="ts">
export default {
    props: {
        num2: {
            type: Number,
            required: true
        },
    },
    methods: {
        updateNum2(event: Event) {
            const target = event.target as HTMLInputElement;
            const value = Number(target.value)
            this.$emit('update:num2', value)
        },
    },
};
</script>

<template>
    <div>
        <input 
            :value="num2" 
            @input="updateNum2" 
            type="number" 
            class="input number-input">
    </div>
</template>

<style>
</style>