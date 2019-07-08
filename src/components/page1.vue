<template>
    <video :src="video" controls autoplay class="video" width="100%"></video>
</template>

<script>
// Use ES6 import to let url-loader recognize this path
// Also, browsers can only play videos with H.264 format
import video from '@/assets/video/fps2_result_h264.mp4';

export default {
  data() {
    return {
      video
    }
  }
}
</script>
