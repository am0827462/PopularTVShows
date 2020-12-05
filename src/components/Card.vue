<!--
    Name: Angela McLaughlin
    Class Section: CIS-131-W01-Fall 2020
    Date: 12/5/2020
-->

<template>
    <div class="card-group">
        <div v-for="show in TVList.slice(0,4)" v-bind:key="show.id">
            <div class="card h-100" style="width: 17rem">
                <img v-bind:src="'https://image.tmdb.org/t/p/w300' + show.poster_path" alt="tvshow">
                <div class="card-body bg-dark">
                    <h5 class="card-title text-white">{{show.name}}</h5>
                    <h5 class="card-title text-info">Vote Average: {{show.vote_average}}</h5>
                    <p class="card-text text-white">{{show.overview}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"Card",
    props:['TVList']
}
</script>