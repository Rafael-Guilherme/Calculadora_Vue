<script lang="ts">
export default {
    props: {
        operator: {
            type: String,
            required: true
        }
    },
    methods: {
        updateOperator(event: Event) {
            const target = event.target as HTMLSelectElement;
            this.$emit('update:operator', target.value) 
        }
    },
};
</script>

<template>
    <div>
        <select 
            :value="operator" 
            @input="updateOperator" 
            class="input input-select">
            <option value="add">+</option>
            <option value="subtract">-</option>
            <option value="multiply">*</option>
            <option value="divide">/</option>
        </select>
    </div>
</template>

<style scoped>
.input-select {
    width: 50px;
    height: 40px;
    margin-bottom: 16px;
}
</style>