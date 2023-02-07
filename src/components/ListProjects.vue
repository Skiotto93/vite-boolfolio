<script>
import axios from "axios";
import CardProject from "./CardProject.vue";

export default {
    name: "ListProjects",
    components: {
        CardProject,
    },
    data() {
        return {
            projects: [],
        }
    },
    created() {
        axios.get('http://127.0.0.1:8000/api/projects')
        .then((res) =>{
            this.projects = res.data;
        });
    }
};
</script>

<template>
    <section>
        <h1>Lista Progetti:</h1>
        <!-- <div class="container">
            <ol>
                <li >
                    {{ project.name }}
                </li>
            </ol>
        </div> -->
        <div class="container-card">
            <ul>
                <li class="project" v-for="project in projects">
                    <CardProject :data="project" />
                </li>
            </ul>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    .container-card {
        max-width: 1200px;
        ul {
            display: flex;
            li {
                list-style: none;
            }
        }
    }
</style>