<template>
    <div id="spotlight" />
</template>

<script setup>
    document.onmousemove = function(e) {
        const mouseXpercentage = Math.round(e.clientX / window.innerWidth * 100),
            mouseYpercentage = Math.round(e.clientY / window.innerHeight * 100);

        const $spotlight = document.getElementById('spotlight');
        $spotlight.style.background = 'radial-gradient( 600px at ' + mouseXpercentage + '% ' + mouseYpercentage + '%, rgba(29, 78, 216, 0.15), transparent 80%)';
    }
    

</script>

<style lang="scss" scoped>

    #spotlight {
        content: "";
        position: fixed;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        inset: 0px;
        background: radial-gradient(600px at center, rgba(29, 78, 216, 0.15), transparent 80%);
        pointer-events: none;
    }
</style>