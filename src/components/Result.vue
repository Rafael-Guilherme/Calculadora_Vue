<script lang="ts">
export default {
    props: {
        value: {
        type: Number,
        required: true
        }
    }
}
</script>

<template>
    <div class="result-container">
        <h2 class="result-title">Resultado: </h2>
        <span class="result">{{ value }}</span>
    </div>
</template>

<style scoped>
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