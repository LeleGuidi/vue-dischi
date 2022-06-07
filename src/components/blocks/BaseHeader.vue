<template>
    <header class="header">
        <img src="../../assets/img/spotify-logo.png" alt="Logo Spotify" class="header_logo">
    </header>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
.header {
    background-color: var(--primary-color);
    // Font size a 0 per rimuovere il bordo inferiore all'immagine
    padding: .625rem 1.25rem;
    font-size: 0;
    &_logo {
        width: 5rem;
    }
}
</style>