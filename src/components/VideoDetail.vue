<template>
    <div v-if="video">
         
        <div class="details">
       <div>
        <iframe :src="videoUrl"> </iframe>
        </div>
            <h4>{{ video.snippet.title}}</h4>
            <p>{{video.snippet.description}}</p>
    </div>
    </div>
</template>

<script>

    export default {
        name:'VideoDetail',
        props:['video'],
        computed: {
            videoUrl() {
                const videoId = this.video.id;
                return `https://www.youtube.com/embed/${videoId}`;
            }
        },
    }
</script>

<style scoped>

</style>