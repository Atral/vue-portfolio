<script setup>
import { onMounted } from 'vue';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faUpRightFromSquare } from '@fortawesome/free-solid-svg-icons'

const props = defineProps({
   experience: {
    type: Object,
    required: true,
   },
});

onMounted(() => {
    const elements = document.querySelectorAll('.experience-box');

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
    <a :href="experience.link" target="_blank">
        <div class="experience-box">
            <div class="dates">{{ experience.startDate }} — {{ experience.endDate }}</div>
            <div class="body">
                <span class="company"><a :href="experience.link" target="_blank">{{ experience.title }} — {{ experience.company }} <FontAwesomeIcon :icon="faUpRightFromSquare" /></a></span>
                <div class="description">
                    <ul>
                        <li v-for="item in experience.description">{{ item }}</li>
                    </ul>
                </div>
                <div class="technologies">
                    <div class="technology" v-for="technology in experience.technologies">{{ technology }}</div>
                </div>
            </div>
        </div>
    </a>
</template>

<style lang="scss" scoped>
    .experience-box {
        width: 100%;
        display: grid;
        grid-template-columns: 30% 70%;
        justify-content: space-evenly;
        font-size: 0.9rem;
        padding: 2rem;
        transition: opacity 0.3s ease-in-out;
        cursor: pointer;

        .dates {
            font-size: 0.8rem;
            margin-right: 1rem;
            text-transform: uppercase;
            font-family: 'Kanit';
            letter-spacing: 0.07em;
        }

        .text-date {
            font-size: .8rem;
            text-transform: uppercase;
        }

        .body {
            .company {
                text-transform: uppercase;
                font-weight: bold;
                color: var(--header-text);
                line-height: 1.8rem;
                pointer-events: all;
                cursor: pointer;

                svg {
                    margin-left: 0.5rem;
                }
            }

            ul {
                margin-left: 0;
                padding-left: 0;
            }
        }
    }

    .experience-box:hover {
        .company {
            a {
                color: var(--main) !important;
                transition: color  0.3s ease-in-out;
            }
        }
    }

    .experience-box.dimmed {
        opacity: 0.5;
    }

    .experience-box.hovered {
        opacity: 1;
    }

    .technologies {
        display: flex;
        flex-wrap: wrap;
        gap: 0.5rem;
        margin-top: 1rem;

        .technology{
            background-color: #00bef334;
            color: var(--main);
            padding: 0.25rem 0.8rem;
            padding-top: 0.4rem;
            border-radius: 1rem;
            text-align: center;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            font-weight: 600;
            line-height: 1;
        }
    }

    @media only screen and (max-width: 1280px) {
        .experience-box {
            padding: 0;
        }
    }
</style>