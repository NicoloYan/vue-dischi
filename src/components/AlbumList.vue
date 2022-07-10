<template>
    <main>
        <div class="container">
            <div class="album_card" v-for="album, index in albumList" :key="index">
                <SingleAlbum :info="album"/>
            </div>
        </div>
    </main>
</template>

<script>
import axios from "axios";
import SingleAlbum from './SingleAlbum.vue';
export default {
    name: 'AlbumList',
    components: {
        SingleAlbum,
    },
    data () {
        return {
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            albumList: [],
        }
    },
    created(){
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            axios.get(this.url).then((result) => {
                this.albumList = result.data.response
            });
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/style.scss';
main {
    background-color: #1e2d3b;
}
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 10px;
    padding: 50px 0;
}
.album_card {
    width: calc((100% / 5) - 40px);
}
</style>