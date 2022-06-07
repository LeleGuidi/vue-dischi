<template>
    <div class="card">
        <div class="card_img">
            <img :src="album.poster" :alt="album.title">
        </div>
        <div class="card_detail">
            <h3>{{album.title}}</h3>
            <h4>{{album.author}}</h4>
            <h4>{{album.year}}</h4>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardAlbum',
    props: {
        album: Object,
    }
}
</script>

<style scoped lang="scss">
.card {
    background-color: var(--primary-color);
    text-align: center;
    color: #758080;
    padding: 1.25rem;
    border-radius: 0;
    border: 0;

    &_img {
        width: 100%;
        height: 0;
        padding-bottom: 100%;
        overflow: hidden;
        margin-bottom: 1rem;

        img {
            object-fit: cover;
            object-position: top;
            width: 100%;
        }
    }

    h3 {
        text-transform: uppercase;
        color: white;
        margin-bottom: 1rem;
    }

    h4 {
        font-size: 0.8rem;
    }
}
</style>