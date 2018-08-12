<template>
    <li class="list-group-item media"  @click="onVideoSelected">
        <div class="mr-3">
        <img :src="imageUrl">
        </div>
        <div class="media-body">
        {{ video.snippet.title}}</div>
    </li>
</template>

<script>
    export default {
        name:'VideoListItem',
        props:['video'],
        computed: {
            imageUrl() {
                return this.video.snippet.thumbnails.default.url;
            }
        },
       methods: {
            onVideoSelected() {
                this.$emit('videoSelect',this.video)
            }
        }
        
    }
</script>

<style scoped>
li {
    display: flex;
    cursor: pointer;
}
li:hover {
    background-color: #eee;
}
</style>