<script setup>
    import Card from '../components/Card.vue'
    import ExperienceBox from '../components/ExperienceBox.vue'
    
    const experiences = [
        {
            title: 'Specialist Software Engineer',
            company: 'Darktrace',
            link: 'https://darktrace.com/',
            startDate: 'MAR 2025',
            endDate: 'PRESENT',
        },
        {
            title: 'Software Engineer',
            company: 'Darktrace',
            link: 'https://darktrace.com/',
            startDate: 'JUL 2021',
            endDate: 'MAR 2025',
            technologies: ['Vue.js', 'Vuetify', 'JavaScript', 'JQuery', 'Node.js', 'MySQL', 'Git', 'HTML & CSS', 'Laravel',],
            description: [
                'Designed and implemented new full-stack systems for the company\'s CRM software, including UI design and implementation, backend and database design.',
                'Created and documented a number of reusable UI components, including a date range selector, comment section and uploader component.',
                'Redesigned legacy systems from the ground up to enhance usability and code quality, as well as reduce the need for manual work during critical periods. For example, I rebuilt our contract amendments system to signifcantly improve user experience and allow more flexibility.',
                'Provided training, guidance and onboarding to junior team members and performed thorough code reviews.',
                'Deployed code to live servers, monitored logs, and resolved server errors.',
                'Stood in as application lead, coordinating scrum activities, communicating with stakeholders, and resolving issues like failed API syncing.'
             ]
        },
        {
            title: 'BSC (HONS) ARTIFICIAL INTELLIGENCE AND COMPUTER SCIENCE, 1ST CLASS',
            company: 'University of Sheffield',
            link: 'https://www.sheffield.ac.uk/undergraduate/courses/2025/computer-science-artificial-intelligence-bsc',
            startDate: '2018',
            endDate: '2021',
            technologies: ['Python', 'Ruby on Rails', 'Haskell', 'Java', 'ROS', 'Robotics', 'Machine Learning', 'Computer Graphics'],
            description: [
                'Led teams in multiple software engineering projects from requirements elicitation through to delivery.',
                'Won the Engineers in Business competition by pitching a swarm robotics solution for precision agriculture.',
                'Wrote my dissertation on AI grammar correction in Python.'
             ]
        },
        {
            title: 'BSc Physics',
            company: 'University of Sheffield',
            link: 'https://www.sheffield.ac.uk/undergraduate/courses/2025/physics-bsc',
            startDate: 'Sep',
            endDate: 'Jul 2016',
            technologies: ['Python'],
            description: [
                'Learned how to use Python in a scientific setting.',
                'Honed skills in advanced mathematics such as Fourier techniques, partial differential equations, and quantum mechanics.',
                'Learned about the physics behind medical imaging technology and how electromagnetic radiation is used in radiography, CT, and MRI.',
                'Found out why aliens haven\'t visited us yet.'
             ]
        }
    ]
</script>

<template>
  <div class="experience section" id="experience">
    <h2 class="section-title">Experience</h2>
    <Card v-for="experience in experiences" >
        <ExperienceBox :experience="experience"/>
    </Card>
  </div>
</template>

<style scoped>
    #experience {
        display: flex;
        flex-direction: column;
        gap: 2rem;

        .section-title {
            margin-bottom: 0;
        }
    }

    @media only screen and (max-width: 1280px) {
        .card { 
            background: none;
            pointer-events: none;
        }
    }
</style>