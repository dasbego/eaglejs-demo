<template lang='pug'>
#IntroTesting.eg-theme-gourmet
  .eg-slideshow
    h1 Intro to Testing
    h2 Presentation for GDG Polymer México - July 2017
    img.logo(src='./gdg_polymer_mexico.png')
</template>

<script>
  import eagle from 'eagle.js'

  var TransitionedSlide = {
    mixins: [eagle.slide],
    props: {
      enter: {default: 'slideInRight'},
      leave: {default: 'slideOutLeft'}
    }
  }
  export default {
    mixins: [eagle.slideshow],
    infos: {
      title: 'Intro to Testing',
      description: 'Presentation for GDG Polymer México - July 2017',
      path: 'Testing'
    },
    components: {
      'v-slide': TransitionedSlide
    },
    props: {
    },
    data () {
    },
    watch: {
    }
  }
</script>

<style lang='scss' scoped>
@import 'node_modules/eagle.js/src/themes/gourmet/gourmet';
#IntroTesting {
  .logo {
    display: block;
    margin: 0 auto;
    max-height: 8em;
  }
  .eg-slideshow {
    .eg-slide {
      .eg-slide-content {
        .demo-slideshow {
          position: relative;
          width: 12rem;
          height: 8rem;
          margin: 0 auto;
        }
      }
    }
  }
  .eg-slideshow.embedded-slideshow-theme {
    background-image: none;
    background-color: white;
  }
}
</style>
