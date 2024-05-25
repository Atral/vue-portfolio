<script setup>
    const props = defineProps({
       text: {
        type: String,
        required: true,
       },
       index: {
        type: Number,
        required: true,
       }
    });

    const addHighlights = (text) => {
        return `<div class="red">${text}</div>`
    }
</script>

<template>
    <div class="introduction-row">
        <div class="line-number">0{{ index + 1 }}</div>
        <div class="text"><h2 v-html="addHighlights(text)"></h2></div>
    </div>
</template>

<style scoped>
    .red { color: red; }

    .introduction-row {
        display: flex;

        .line-number {
            margin: 0;
            font-size: 1.5rem;
            margin-right: 20px;
            color: var(--natural);
        }
        .text {
            overflow: hidden;
            display: grid;

            h2 {
                margin: 0;
                font-size: 1.8rem;
                grid-row: 1;
                grid-column: 1;
                padding-right: 10px;
                white-space: nowrap;
            }
        }
    }
</style>