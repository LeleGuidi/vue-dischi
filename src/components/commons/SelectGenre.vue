<template>
<div>
    <label for="genre">Seleziona un genere</label>
    <select v-model="DataShared.SelectedGenre" id="genre">
        <option value>Tutti i generi</option>
        <option v-for="(genre, index) in takeGenre" :key="index">{{genre}}</option>
    </select>
</div>
    
</template>

<script>
import DataShared from '../../shared/DataShared'
export default {
    name: 'SelectAlbum',
    data() {
        return {
            DataShared,
        }
    },
    computed: {
        takeGenre() {
            let AllGenre = []
            for (let i = 0; i < this.DataShared.Albums.length; i++) {
                if (!AllGenre.includes(this.DataShared.Albums[i].genre)) {
                    AllGenre.push(this.DataShared.Albums[i].genre)
                }
            }
            return AllGenre
        }
    }
}
</script>

<style lang="scss" scoped>
    select {
        border: 0;
        background-color: #1ed760;
        color: #191716;
        padding: 0.3rem 0.8rem;
    }
    label {
        font-size: 1rem;
        padding-right: 1.5rem;
        color: white;
    }
</style>