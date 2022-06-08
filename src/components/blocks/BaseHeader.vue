<template>
    <header class="header">
        <img src="../../assets/img/spotify-logo.png" alt="Logo Spotify" class="header_logo">
        <SelectGenre class="header_select"/>
    </header>
</template>

<script>
import SelectGenre from '../commons/SelectGenre.vue'

export default {
    components: { 
        SelectGenre 
    },
    
}
</script>

<style lang="scss" scoped>
.header {
    background-color: var(--primary-color);
    // Font size a 0 per rimuovere il bordo inferiore all'immagine
    padding: .625rem 1.25rem;
    font-size: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    &_logo {
        width: 3.5rem;
    }
}
</style>