<template>
    <main>
        <div class="container">
            <div class="album_card" v-for="album, index in setActiveGenre" :key="index">
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
            filteredArray: []
        }
    },

    props: {
        selectedGenre: String,
    },

    created(){
        this.getAlbums();
    },

    computed: {
        setActiveGenre() {
            let filteredArray = [];
            if (this.selectedGenre == "") {
                filteredArray = this.albumList
            } 
            else if (this.selectedGenre == "All") {
                filteredArray = this.albumList
            } else {
                filteredArray = this.albumList.filter((element) => {
                    if (element.genre == this.selectedGenre) {
                        return element;
                    }
                })
            }
            return filteredArray;
        },
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