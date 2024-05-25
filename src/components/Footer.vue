<script setup>

</script>

<template>
    <div class="footer">
       Website was coded by Jack Maskell from scratch in <a href="https://code.visualstudio.com/">Visual Studio Code</a>. Built using <a href="https://vuejs.org/">Vue.js</a> and <a href="https://vitejs.dev/">Vite</a> and deployed with <a href="https://vercel.com/">Vercel.</a>
    </div>
</template>


<style lang="scss" scoped>
    .footer {
        font-size: 0.9rem;

        a {
            color: var(--header-text);
            font-weight: bold;
            text-decoration: none;
        }

        a:hover {
            color: var(--main);
            transition: color 0.15s linear;
        }
    }
</style>