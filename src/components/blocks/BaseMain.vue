<template>
    <div class="main">
        <SectionAlbum/>
    </div>
</template>

<script>
import SectionAlbum from '../sections/SectionAlbum.vue'

export default {
    name: 'BaseMain',
    components: {
        SectionAlbum
    }
}
</script>

<style lang="scss" scoped>
.main {
    background-color: var(--secondary-color);
    min-height: calc(100vh - 3.875rem);
}
</style>