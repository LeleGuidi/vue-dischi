<template>
    <div class="select">
        <label for="genre">Seleziona un genere interessato</label>
        <select name="genre" id="genre">
            <option value="">Tutti i generi</option>
            <option v-for="(genre, index) in AllGenre" :key="index" :value="AllGenre">{{AllGenre}}</option>
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
            AllGenre: [],
        }
    },
    created() {
        for (let i = 0; i < this.DataShared.Albums.length; i++) {
            if (!this.AllGenre.includes(this.DataShared.Albums[i].genre)) {
                this.AllGenre.push(this.DataShared.Albums[i].genre)
            }
        }
        console.log(this.AllGenre)
        
    }
}
</script>

<style lang="scss" scoped>

</style>