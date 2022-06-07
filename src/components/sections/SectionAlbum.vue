<template>
    <section class="SectionAlbum container_main">
        <div class="row_main">
            <CardAlbum class="col_main" v-for="(album, index) in albums" :key="index" :album="album"/>
        </div>
    </section>
</template>

<script>
import CardAlbum from '../commons/CardAlbum.vue';
import axios from 'axios'

export default {
    components: { 
        CardAlbum 
    },
    data() {
        return {
            albums: [],
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.albums = response.data.response
            console.log(response.data.response)
        })
    }
    
}
</script>

<style lang="scss" scoped>
.container_main {
    max-width: 68.75rem;
    margin: auto;
    padding: 2rem 1.5rem;

    .row_main {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 1rem 1.5rem;
    }

    .col_main {
        width: calc(100% / 2 - .75rem);
    }
}

@media screen and (min-width: 992px) {
    .col_main {
        width: calc(100% / 5 - .75rem);
    }
}

@media screen and (min-width: 768px) {
    .col_main {
        width: calc(100% / 3 - .75rem);
  }
}
</style>