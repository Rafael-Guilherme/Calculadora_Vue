<script lang="ts">
import Result from './Result.vue';
import Operator from './OperatorSelect.vue'
import Input1 from './InputNum1.vue'
import Input2 from './InputNum2.vue'

export default {
    components: {
        Input1,
        Input2,
        Result,
        Operator
    },
    data() {
        return {
        num1: 0,
        num2: 0,
        operator: 'add'
        };
    },
    computed: {
        result() {
        switch (this.operator) {
            case 'add':
            return this.num1 + this.num2;
            case 'subtract':
            return this.num1 - this.num2;
            case 'multiply':
            return this.num1 * this.num2;
            case 'divide':
            return this.num1 / this.num2;
            default:
            return 0;
        }
        }
    }
};
</script>

<template>
    <div class="container">
        <Input1 
            :num1="num1"
            @update:num1="num1 = $event"
        />
        <Operator 
            v-bind:operator="operator" 
            v-on:update:operator="operator = $event"
        />
        <Input2 
            :num2="num2"
            @update:num2="num2 = $event"
        />
        <Result :value="result" />
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
}
</style>