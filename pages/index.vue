<template>
  <div class="main-container">
    <iframe src="/audio/silence.mp3" allow="autoplay" style="display: none;" frameborder="0"></iframe>
    <audio
      id="bg_audio"
      autoplay
      loop
      src="/audio/audio1.mp3" ref="bg_audio_ref">
      Your browser does not support the
      <code>audio</code> element.
    </audio>
    <Cover/>
    <Content/>
  </div>
</template>

<script>
import Cover from "../components/Cover.vue"
import Content from "../components/Content.vue"
export default {
  name: 'IndexPage',
  component: {
    Cover,
    Content
  },
  head() {
    return {
      title: 'Wawan & Dheta',
      meta: [
        {
          hid: 'og:title', property: 'og:title', content: 'Undangan Pernikahan Wawan & Dheta'
        },
        {
          hid: 'og:description', property: 'og:description', content: 'Undangan Pernikahan Wawan & Dheta'
        },
        {
          hid: 'og:image', property: 'og:image', content: 'https://raw.githubusercontent.com/juniantowicaksono06/wawan-dan-dheta/main/static/img/icon.jpg'
        },
        {
          hid: 'og:image:secure_url', property: 'og:image:secure_url', content: 'https://raw.githubusercontent.com/juniantowicaksono06/wawan-dan-dheta/main/static/img/icon.jpg'
        },
        {
          hid: 'og:image:type', property: 'og:image:type', content: 'image/jpeg'
        },
        {
          hid: 'og:image:width', property: 'og:image:width', content: '256'
        },
        {
          hid: 'og:image:height', property: 'og:image:height', content: '256'
        },
      ]
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      this.initBgAudio()
    })
  },
  methods: {
    initBgAudio() {
      this.$refs.bg_audio_ref.play()
    }
  }
}
</script>
