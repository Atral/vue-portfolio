<script setup>
import { onMounted } from 'vue';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faCode, faFilePdf } from '@fortawesome/free-solid-svg-icons';
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons';

let currentSection = 'about';

onMounted(() => {
    const navLinkEls = document.querySelectorAll('.nav-link');
    const sectionEls = document.querySelectorAll('.section');

    window.addEventListener('scroll', () => {
        const bottomVisible = document.documentElement.clientHeight + window.scrollY >= (document.documentElement.scrollHeight || document.documentElement.clientHeight);

        sectionEls.forEach(sectionEl => {
            if (window.scrollY + (14 * parseFloat(getComputedStyle(document.documentElement).fontSize)) >= sectionEl.offsetTop) {
                currentSection = sectionEl.id;
            }
        });
        
        if (bottomVisible) {
            currentSection = 'contact';
        }

        navLinkEls.forEach(navLinkEl => {
            if (navLinkEl.getAttribute('data-target') === currentSection) {
                navLinkEl.classList.add('active-nav-link');
            } else {
                navLinkEl.classList.remove('active-nav-link');
            }
        });
    });
});

const scrollToPosition = (e) => {
    e.preventDefault();
    const targetId = e.target.getAttribute('data-target');
    const targetElement = document.getElementById(targetId);
    if (targetElement) {
        window.scrollTo({
            top: targetElement.offsetTop,
            behavior: 'smooth'
        });
    }
};
</script>

<template>
    <div class="navbar">
        <div class="container">
            <h1>Jack Maskell</h1>
            <h2 class="sub-heading">Full-Stack Software Engineer</h2>
            <div class="main-text">I build clean, scalable web applications in JavaScript.</div>
            <div class="links">
                <div class="nav-link active-nav-link" data-target="about" @click="scrollToPosition">About</div>
                <div class="nav-link" data-target="experience" @click="scrollToPosition">Experience</div>
                <div class="nav-link" data-target="stats" @click="scrollToPosition">Stats</div>
                <div class="nav-link" data-target="projects" @click="scrollToPosition">Projects</div>
                <div class="nav-link" data-target="contact" @click="scrollToPosition">Contact</div>
            </div>
            <div class="icons">
                <a href="https://github.com/Atral" target="_blank"><FontAwesomeIcon :icon="faGithub" /></a>
                <a href="https://www.linkedin.com/in/jack-maskell/" target="_blank"><FontAwesomeIcon :icon="faLinkedin" /></a>
                <a href="https://github.com/Atral/vue-portfolio" target="_blank"><FontAwesomeIcon :icon="faCode" /></a>
                <a href="https://drive.google.com/uc?export=download&id=1ufg843CinuieU4zJKahbxp9mwklroREC" download="jack-maskell-cv.pdf"><FontAwesomeIcon :icon="faFilePdf" /></a>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .navbar {
        width: 48%;

        .main-text {
            margin-top: 1.125rem;
            width: 52%;
        }

        .container {
            position: fixed;
        }

        .links {
            margin-top: 4rem;

            .nav-link {
                padding-top: 12px;
                padding-bottom: 12px;
                text-transform: uppercase;
                font-size: .8rem;
                font-weight: bold;
                letter-spacing: 0.15rem;
                cursor: pointer;
                display: block;
                height: 48px;
            }

            .nav-link:hover {
                color: var(--header-text);
                transition: var(--text-hover-transition);
            }
        }

        .icons {
            display: flex;
            gap: 1.5rem;
            font-size: 1.6rem;
            bottom: 6rem;
            position: fixed;

            svg {
                transition: color 0.1s ease-in-out;
                cursor: pointer;
            }

            svg:hover {
                color: var(--header-text);
            }
        }
    }

    @media only screen and (max-width: 1280px) {
        .navbar {
            width: 100%;
            position: relative;

            .container {
                position: relative;
            }

            .links {
                display: none;
            }

            .main-text {
                width: 100%;
            }

            .icons {
                top: unset;
                position: unset;
                margin-top: 2rem;
            }
        }
    }
</style>