<script>
export default {
    name: "CardProject",
    props: {
        data: Object,
    }
}
</script>

<template>
    <section>
        <div class="card">
            <div class="card-body">
                <h3>{{ data.name }}</h3>
                <img v-if="data.image_url" :src="data.image_url" :alt="data.name">
                <p>{{ data.description }}</p>
                <h5>{{ data.name_client }}</h5>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    section {
        max-width: 1400px;
        .card{
            width: 400px;
        }
    }
</style>