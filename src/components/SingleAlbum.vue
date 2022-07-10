<template>
  <div class="single_album">
        <div class="img-container">
            <img :src="info.poster" :alt="info.title">
        </div>
        <h3>
            {{info.title}}
        </h3>
        <div class="author">
            {{info.author}}
        </div>
        <div class="year">
            {{info.year}}
        </div>
    </div>
</template>

<script>
export default {
    name: 'SingleAlbum',
    props: ['info'],
}
</script>

<style lang="scss" scoped>
.single_album {
    margin-top: 15px;
    background-color: #2e3a46;
    height: 300px;
    padding: 20px;
}
h3 {
    color: white;
    text-transform: uppercase;
    margin: 10px 0;
    text-align: center;
}
img {
    width: 100%;
}
.author {
    color: #686765;
    text-align: center;
}
.year {
    color: #686765;
    text-align: center;
}
</style>