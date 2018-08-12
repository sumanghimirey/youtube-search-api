<template>
<div>
    <ul>
     <VideoListItem 
     v-for="video in videos"
      :key="video.id.videoId"
      :video="video">
        
         </VideoListItem>
    </ul>
    </div>
</template>

<script>
import VideoListItem from './VideoListItem';
    export default {
        
        name:'VideoList',
        props:['videos'],
        components:{
            VideoListItem
        }
        
    }
</script>

<style scoped>

</style>