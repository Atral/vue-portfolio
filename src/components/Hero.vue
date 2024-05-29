<script setup>
    import IntroductionRow from '../components/IntroductionRow.vue'
    
    const getYearsSince = (date) => {
        const since = new Date(date);
        const diffMillis = Math.abs(new Date() - since);
        const diffYears = Math.round(diffMillis / (1000 * 60 * 60 * 24 * 365));

        return `${diffYears} years`
    }

</script>

<template class="hero">
    <div class="hero section" id="about">
        I was studying physics at university when had my first proper go at programming. My first language was <a href="https://www.python.org/" target="_blank">Python</a>. 
        It scratched an itch that physics didn't. I could write some code, click a button, and see the fruits of my labour immediately. I loved it.<br/><br/>
    
        I decided to switch degrees and study <a href="https://www.sheffield.ac.uk/undergraduate/courses/2025/computer-science-artificial-intelligence-bsc" target="_blank"> Artificial Intelligence and Computer Science</a> and while studying, I discovered web development. It perfectly combined my passion for programming and my many years of interest in graphic design. After graduating, I started looking for jobs in web development and landed one at Darktrace. For the past three years, I've been working as a full-stack engineer on the company's CRM, planning, designing, and coding new systems to support the business's sales operations. <br/><br/>
    </div>

</template>

<style scoped>
    .hero {
        a {
            color: var(--header-text);
            font-weight: bold;
            text-decoration: none;
        }

        a:hover {
            color: var(--main);
            transition: color 0.15s linear;
        }
    }
</style>