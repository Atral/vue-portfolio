<script setup>
import { onMounted } from 'vue';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faUpRightFromSquare } from '@fortawesome/free-solid-svg-icons'
import Quotes from '@/components/Quotes.vue'

    const props = defineProps({
        project: {
            type: Object,
            required: true,
        },
    });

    onMounted(() => {
        const elements = document.querySelectorAll('.project');

        elements.forEach(element => {
            element.addEventListener('mouseenter', () => {
                elements.forEach(el => {
                    el.classList.toggle('dimmed', el !== element);
                    el.classList.toggle('hovered', el === element);
                });
            });

            element.addEventListener('mouseleave', () => {
                elements.forEach(el => {
                    el.classList.remove('dimmed', 'hovered');
                });
            });
        });
    });
</script>

<template>
    <div class="project">
        <img :src="project.image" :alt="project.alt"/>
        <div class="content">
            <div class="title"><a :href="project.link" target="_blank">{{ project.name }} <FontAwesomeIcon :icon="faUpRightFromSquare" /></a></div>
            <div class="description">{{ project.description }}</div>
            <Quotes :quotes="project?.quotes" v-if="project.quotes"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .project {
        display: flex;
        gap: 2rem;
        padding: 2rem;

        transition: opacity 0.3s ease-in-out;

        img {
            width: 30%;
            height: 30%;
            aspect-ratio: 1;
            opacity: 0.75;
            border-radius: 0.25rem;
        }
        
        .content {
            display: flex;
            gap: 1rem;
            flex-direction: column;

            .title {
                text-transform: uppercase;
                font-size: 0.9rem;
                font-weight: 800;
                color: var(--header-text);
                pointer-events: all;
                cursor: pointer;

                svg {
                    margin-left: 0.5rem;
                }
            }
        }
    }

    .project:hover {
        .title {
            color: var(--main) !important;
            transition: color  0.3s ease-in-out;
        }

        img {
            opacity: 1;
            transition: 0.3s ease-in-out;
        }
    }

    .project.dimmed {
        opacity: 0.5;
    }

    .project.hovered {
        opacity: 1;
    }

    @media only screen and (max-width: 1280px) {
        .project {
            flex-direction: column-reverse;
            padding: 0;
            pointer-events: none;
        }

        .project.dimmed {
            opacity: unset;
        }
    }
</style>