<script setup>
    import Card from '../components/Card.vue'
    import ExperienceBox from '../components/ExperienceBox.vue'
    
    const experiences = [
        {
            title: 'Software Engineer',
            company: 'Darktrace',
            link: 'https://darktrace.com/',
            startDate: '2021',
            endDate: 'Present',
            technologies: ['Vue.js', 'Vuetify', 'JavaScript', 'Node.js', 'MySQL', 'Git', 'HTML & CSS', 'Laravel',],
            description: [
                'Designed and implemented new systems across the whole stack for the company\'s CRM software.',
                'Redesigned legacy systems from the ground up, to enhance usability and code quality and reduce the need for manual work during critical periods.',
                'Provded training and guidance to junior team members and performed thorough code reviews.',
                'Deployed code to live servers, monitored logs and resolved server errors.',
                'Stood in as application lead, coordinating scrum activities, communicating with stakeholders and resolving issues like failed API syncing.'
             ]
        },
        {
            title: 'BSc (Hons) Artifical Intelligence and Computer Science, 1st Class',
            company: 'University of Sheffield',
            link: 'https://www.sheffield.ac.uk/undergraduate/courses/2025/computer-science-artificial-intelligence-bsc',
            startDate: '2018',
            endDate: '2021',
            technologies: ['Python', 'Ruby on Rails', 'Haskell', 'Java', 'ROS', 'Robotics', 'Machine Learning', 'Computer Graphics'],
            description: [
                'Led teams in multiple software engineering projects from requirements elicitation through to delivery.',
                'Won the Engineers in Business competition by pitching a swarm robotics solution for precision agriculture.',
                'Wrote my disseration on AI grammar correction in Python.'
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
                'Honed skills in advanced mathematics such as Fourier techniques and partial differential equations and quantum mechanics.',
                'Learned about physics behind medical imaging technology and how electromagnetic radiation is used in radiography, CT and MRI.',
                'Found out why aliens haven\'t visted us yet.'
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