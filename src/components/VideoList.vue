<template>
<div>
    <ul class="list-group col-md-6" >
     <VideoListItem 
     v-for="video in videos"
      :key="video.id.videoId"
      :video="video" @videoSelect="onVideoSelected">
        
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
        },
        methods: {
            onVideoSelected(video) { 
                this.$emit('onSelectedVideo', video)
            }
        },
        
        
    }
</script>

<style scoped>

</style>