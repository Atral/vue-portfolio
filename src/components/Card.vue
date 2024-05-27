<template>
    <div class="card">
        <slot></slot>
    </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
    .card {
        position: relative;
        margin: 0 auto;
        width: -webkit-fill-available;
        display: flex;
        align-items: center;
        border-radius: 0.5rem;
        border: 1px solid transparent;
    }

    .card:hover {
        background-color: rgba(57, 53, 94, 0.226);
        box-shadow: 0px 0 12px 0px rgb(0 0 0 / 6%);
        backdrop-filter: blur(15px);
        border: 1px solid rgba(90, 66, 156, 0.212);
        transition-property: background-color, box-shadow, backdrop-filter, border;
        transition-duration: 0.3s;
        transition-timing-function: ease-in-out;
    }

    @media only screen and (max-width: 1280px) {
        .card {
            background-color: transparent;
            border: none;
            backdrop-filter: none;
            box-shadow: none;
            pointer-events: none;
        }

        .card:hover {
            background-color: transparent;
            border: none;
            backdrop-filter: none;
            pointer-events: none;
        }
    }

</style>