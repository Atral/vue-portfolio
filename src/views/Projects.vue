<script setup>
    import cfpImage from '../assets/images/cfp.png';
    import diceRollImage from '../assets/images/dice-roll.png';
    import kateYangImage from '../assets/images/kate-yang.png';
    import coinIdentifierImage from '../assets/images/coin-identifier.png';

    import Card from '@/components/Card.vue';
    import Project from '@/components/Project.vue'

    const projects = [
        {   
            image: cfpImage,
            altText: '3 characters wearing medieval attire.',
            name: 'Community Flavor Pack',
            link: 'https://steamcommunity.com/sharedfiles/filedetails/?id=2220098919',
            description: 'I am part of the a core team of 2 on Community Flavor Pack, the most popular Crusader Kings 3 mod with 500,000 downloads, where my contributions mostly include 2D graphics and textures. The project adds historically accurate and documented visual flavour to the game to enhance visual flavour without affecting balance or gameplay.',
            quotes: [
                { author: 'PC Gamer', quote: 'Honestly, it\'s difficult to tell this is even a mod.' },
                { author: 'Wargamer', quote: 'You might have constructed a mighty realm, but have you done it in style?' },
                { author: 'PC Magazin', quote: 'The new features fit seamlessly into the game without disturbing the immersion' },
                { author: 'Game Rant', quote: 'Arguably the best mod for Crusader Kings 3' },
            ]
        },
        {   
            altText: 'Screenshot of a clothing website.',
            image: kateYangImage,
            name: 'Kate Yang',
            link: 'https://kateyang.co.uk',
            description: 'I\'m currently building an e-commerce shop to sell traditional Chinese clothing using Vue.js, node.js and mySQL.'
        },
        {   
            altText: 'Screenshot of a coin identifier website.',
            image: coinIdentifierImage,
            name: 'Coin Identifier',
            link: '',
            description: 'A tool to help you identify English coinage of the Middle Ages, built in Vue.js.'
        },
        {   
            altText: 'Screenshot of dice being thrown on a board.',
            image: diceRollImage,
            name: 'Dice Roll App for Tabletop Games',
            link: 'https://github.com/Atral/dice_roll',
            description: 'I\'m building a physics based dice roll app designed to be used for tabletop games. The app is built in Unity Engine using C#.'
        },
    ]
</script>

<template>
    <div class="section" id="projects">
        <h2 class="section-title">Projects</h2>
        <a v-for="project in projects"  :href="project.link" target="_blank">
            <Card>
                <Project :project="project" />
            </Card>
        </a>
    </div>
</template>

<style scoped>
    #projects {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        .section-title {
            margin: 0;
        }
    }
</style>