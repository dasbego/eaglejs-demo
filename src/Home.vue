<template lang='pug'>
.frontpage
  .content
    h1
      span.logo
    h2 Guillermo Beltran - Frontend Developer @Segundamano.mx

    p.
      Eagle.js is a web-based slideshow framework for Vue.js.
      It supports animations, themes, interactive widgets (for web demos),
      and makes it easy to reuse components, slides and styles across presentations.

    .thumbnails
      .box-card(v-for='slideshow in slideshows')
        router-link(:to='slideshow.infos.path' @click.native="click")
          .embedded-slideshow-container
            component(:is="slideshow", :embedded='true',
                      :keyboardNavigation='false',
                      :mouseNavigation='false')
        .caption
          h3 {{slideshow.infos.title}}
          p.thumbnail-description {{slideshow.infos.description}}

    p.home-footer.
      These presentations are powered by <a href='https://github.com/zulko/eagle.js/' target='_blank' style="text-decoration: underline;">Eagle.js</a>. A hackable slideshow framework built with Vue.js
</template>

<script>
import slideshows from 'slideshows/slideshows'

export default {
  data: function () {
    return {
      slideshows: slideshows.list
    }
  },
  mounted: function () {
    document.currentSlide = {}
  },
  methods: {
    click: function (evt) {
      evt.stopPropagation()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
@import "node_modules/eagle.js/src/themes/frontpage/frontpage";
.logo {
  display: inline-block;
  width: 130px;
  height:90px;
  margin-right: 0.1em;
  background-image: url(./logo.svg);
  background-size: contain;
  background-position: center bottom;
  background-repeat: no-repeat;
}

.home-footer {
  font-size: 14px;
  text-align: center;
}
</style>
