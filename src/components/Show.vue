<template>
    <!-- Layout for the bootstrap cards -->
    <!-- Uses data passed from Card.vue which was inherited by the App.Vue compoenent -->
    <div class="card">
            <img class="card-img-top" :src="'https://image.tmdb.org/t/p/w342' + aShow.poster_path" alt="Movie Poster Picture">
            <div class="card-body">
                <h3 class="card-title">{{aShow.name}}</h3>
                <p class="card-body">{{aShow.overview}}</p>
            </div>
        </div>
</template>
<script>
export default {
    // Name of component
    name: "Show",
    // aShow prop which is a individual show that was gathered from the v-for in Card.vue
    props: [
        'aShow'
    ]
}
</script>
<style scoped>
/* Styles for each card */
img {
    max-width:100%;
}
/* Attempts to center every card as close to the middle as it can get without messing up any other cards */
.card {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 500px;
    height: max-content;
}
h3 {
    text-decoration: underline;
}
</style>