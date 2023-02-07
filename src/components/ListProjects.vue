<script>
import axios from "axios";

export default {
    name: "ListProjects",
    data() {
        return {
            projects: [],
        }
    },
    created() {
        axios.get('http://127.0.0.1:8000/api/projects')
        .then((res) =>{
            console.log(res)
        });
    }
};
</script>

<template>
    <section>
        <h1>Lista Progetti:</h1>
    </section>
</template>

<style lang="scss" scoped>

</style>