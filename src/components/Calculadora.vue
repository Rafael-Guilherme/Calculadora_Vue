<script lang="ts">
export default {
    data() {
        return {
        num1: 0,
        num2: 0,
        operator: "add",
        };
    },
    computed: {
        result() {
            switch (this.operator) {
                case "add":
                return this.num1 + this.num2;
                case "subtract":
                return this.num1 - this.num2;
                case "multiply":
                return this.num1 * this.num2;
                case "divide":
                return this.num1 / this.num2;
                default:
                return 0;
            }
        },
    },
};
</script>

<template>
    <div class="container calculator-container">
        <div class="container inputs-container">
            <input v-model="num1" type="number" class="input number-input">
            <select v-model="operator" class="input input-select">
            <option value="add">+</option>
            <option value="subtract">-</option>
            <option value="multiply">*</option>
            <option value="divide">/</option>
            </select>
            <input v-model="num2" type="number" class="input number-input">
        </div>
        <div class="result-container">
            <h2 class="result-title">Resultado: </h2>
            <span class="result">{{ result }}</span>
        </div>
    </div>
</template>

<style scoped>

.container {
    display: flex;
    align-items: center;
    justify-content: center;
}
.calculator-container {
    flex-direction: column;
    height: 100vh;
}

.inputs-container {
    margin-bottom: 1rem;
}

.input {
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 0.25rem;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
    font-size: 1rem;
    line-height: 1.5rem;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}

.number-input {
    width: 100px;
}

.input-select {
    width: 50px;
    height: 40px;
    margin: 0 8px;
}

.result-container {
    display: flex;
    align-items: center;
    justify-content: center;
}

.result-title {
    font-weight: bold;
    margin-right: 8px;
}

.result {
    font-size: 1.5rem;
    font-weight: bold;
}
</style>