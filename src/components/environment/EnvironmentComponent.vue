<script setup>
const meta = import.meta.env;
const title = meta.VITE_TITLE
</script>

<template>
    <div class="footer"> 
        <p>{{ title }}</p>
    </div>
</template>

<style scoped lang="scss">
    .footer {
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        padding: 0.3rem 0.7rem;
        background-color: #333;
        color: white;
        z-index: 1;
        font-size: 0.75rem;

        p {
            font-family: monospace;
        }
    }
</style>