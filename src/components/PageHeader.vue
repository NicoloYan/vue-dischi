<template>
    <div>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Spotify_icon.svg/1982px-Spotify_icon.svg.png" alt="logo spotify">
        <div>
            <label for="">Select genre</label>
            <select 
                name="genre"
                id="genre" 
                v-model="selectedOption" 
                @change="$emit('changeGenre', selectedOption)"
                >
                <option value="All">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Metal">Metal</option>
                <option value="Jazz">Jazz</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PageHeader',
    data () {
        return {
            selectedOption: 'All',
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/style.scss';
img {
    width: 70px;
    padding: 15px;
}
div {
    background-color: $page_main_color;
}
</style>