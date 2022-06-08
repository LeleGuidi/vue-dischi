<template>
    <section class="SectionAlbum container_main">
        <div class="row_main">
            <CardAlbum class="col_main" v-for="(album, index) in albums" :key="index" :album="album"/>
        </div>
    </section>
</template>

<script>
import CardAlbum from '../commons/CardAlbum.vue';
import axios from 'axios';
import DataShared from '../../shared/DataShared.js';

export default {
    components: { 
        CardAlbum,
    },
    data() {
        return {
            albums: [],
            DataShared
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.albums = response.data.response
            this.DataShared.Albums = response.data.response
        })
    }
    
}
</script>

<style lang="scss" scoped>
.container_main {
    max-width: 68.75rem;
    margin: auto;
    padding: 1.5rem 1.5rem;

    .row_main {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 1rem 1.5rem;
    }

    .col_main {
        width: calc(100% / 5 - 1.2rem);
    }
    @media screen and (max-width: 36rem) {
        .col_main {
            width: calc(100% / 2 - 1.2rem);
        }
    }
    @media screen and (max-width: 48rem) {
        .col_main {
            width: calc(100% / 3 - 1.2rem);
        }
    }
}


</style>