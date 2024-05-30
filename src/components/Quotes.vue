<script setup>
    const props = defineProps({
        quotes: {
            type: Object,
            required: true,
        },
    });

</script>

<template>
    <v-carousel cycle :show-arrows="false" hide-delimiters height="4rem">
        <v-carousel-item v-for="(quote, i) in quotes" :key="i" reverse-transition="fade-transition" transition="fade-transition">
            <div class="quote-container">
               "{{ quote.quote }}"<br/>
                <div class="author">― {{ quote.author }}</div>
            </div>
        </v-carousel-item>
    </v-carousel>
</template>


<style lang="scss" scoped>
 .quote-container {
    font-size: 0.9rem;
    font-style: italic;
    color: #72a4e7d9;

    .author {
        font-size: 0.8rem;
        color: var(--header-text);
        margin-left: 0.5rem;
    }
 }
</style>