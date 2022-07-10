<template>
    <div>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Spotify_icon.svg/1982px-Spotify_icon.svg.png" alt="logo spotify">
    </div>
</template>

<script>
export default {
    name: 'PageHeader'
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