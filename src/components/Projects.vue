<script>
import ProjectCard from './ProjectCard.vue';
import axios from 'axios';


export default {
    components: {
        ProjectCard,
    },

    name: 'Projects',

    data() {
        return{
            projects: []
        };
    },

    methods: {
        getProjectsFromApi() {
            axios.get('http://127.0.0.1:8000/api/projects')
            .then((response) => {
                this.projects = response.data.results;
            });
        }
    },
    mounted() {
        this.getProjectsFromApi();
    },
}
</script>

<template>
    <div class="container">
        <h1>Projects</h1>

        <div class="container text-center d-flex flex-wrap">
            <div v-for="project in projects">
                <ProjectCard :projectInfo="project"></ProjectCard>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@use '../style/generic';


</style>