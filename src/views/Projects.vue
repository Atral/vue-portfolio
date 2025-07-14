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
            link: 'https://communityflavorpack.com/',
            description: `For four years, I have been part of a core team of two on Community Flavor Pack, the most popular Crusader Kings 3 mod. The project adds historically accurate and documented visual flavour to the game to enhance the experience without affecting balance or gameplay. My contributions of 2D graphics, textures, and game code have helped the mod grow to over 500,000 downloads.`,
            quotes: [
                { id: 1, author: 'PC Gamer', quote: 'Honestly, it\'s difficult to tell this is even a mod.' },
                { id: 2, author: 'Wargamer', quote: 'You might have constructed a mighty realm, but have you done it in style?' },
                { id: 3, author: 'PC Magazin', quote: 'The new features fit seamlessly into the game without disturbing the immersion' },
                { id: 4, author: 'Game Rant', quote: 'Arguably the best mod for Crusader Kings 3' },
            ]
        },
        {   
            altText: 'Screenshot of a clothing website.',
            image: kateYangImage,
            name: 'Kate Yang',
            link: 'https://kateyang.co.uk',
            description: 'I\'m running an e-commerce shop selling traditional Chinese clothing. Through this I\'ve gained skills in photo editing, search engine optimisation, load speed optimisation and learned how to design websites to maximise conversions.' 
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
            description: 'I\'m building a physics based dice roll app designed to be used for tabletop games. The app is built in Unity Engine using C#. This project was my introduction to C#, graphics optimisation and android app programming.'
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