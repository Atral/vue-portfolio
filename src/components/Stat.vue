<script setup>
    const props = defineProps({
        stat: {
            type: Object,
            required: true,
        },
    });
</script>

<template>
    <div class="stat">
        <div class="label">{{ stat.label }}</div>
        <div class="amount">{{ stat.amount }}</div>
    </div>
</template>

<style lang="scss" scoped>
    .stat {
        padding: 0.7rem 1rem ;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        height: 5rem;
        text-align: center;

        .label {
            text-transform: uppercase;
            font-weight: 800;
            font-size: 0.7rem;
        }

        .amount {
            color: var(--header-text);
        }
    }

    .stat:hover {
        .amount {
            color: var(--main);
            transition: color 0.2s linear;
            
        }

        .label {
            color: var(--header-text);
            transition: color 0.2s linear;
        }
    }
</style>