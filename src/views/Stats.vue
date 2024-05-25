<script setup>
import Card from '@/components/Card.vue';
import Stat from '@/components/Stat.vue';

const stats = [
    { label: 'Years as a developer', amount: 3 },
    { label: 'MRs Deployed', amount: 273 },
    { label: 'Bugs Squashed', amount: 53 },
    { label: 'Major Projects', amount: 7 },
    { label: 'Countries Visited', amount: 6 },
    { label: 'CK3 Playtime', amount: '417 h' },
]

</script>

<template>
    <div id="stats">
        <h2 class="section-title">Stats</h2>
        <div class="section" id="stats-container">
            <Card v-for="stat in stats">
                <Stat :stat="stat"/>
            </Card>
        </div>
    </div>
</template>

<style scoped>
    #stats-container {
        display: grid;
        grid-template-columns: 33% 31% 31%;
        gap: 1rem;

        .card {
            width: auto;
            background-color: rgba(57, 53, 94, 0.226);
            box-shadow: 0px 0 12px 0px rgb(0 0 0 / 6%);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(90, 66, 156, 0.212);
            width: 100%;
            cursor: default;
        }

        .card:hover {
            background-color: rgba(79, 75, 117, 0.226);
            transition: background-color 0.2s linear;
        }
    }
</style>