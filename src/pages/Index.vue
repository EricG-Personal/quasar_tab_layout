<template>
  <q-page class="column page-background">

    <q-resize-observable @resize="onResize" />

    <q-scroll-area :style="styleScrollArea">

      <!-- <div>
        top
      </div> -->

      <div v-for="n in 500" :key="n.id">
        Lorem ipsum dolor sit amet, consectetur adipisicing
        elit, sed do eiusmod tempor incididunt ut labore et
        dolore magna aliqua2.
      </div>

      <!-- <div class="scroll-area-content">
        bottom
      </div> -->

    </q-scroll-area>

  </q-page>
</template>

<style>
</style>

<script>

import { dom } from 'quasar'
const { height } = dom

export default {
  name: 'PageIndex',

  mounted: function () {
    console.log('is mounted')

    this.pageHeight = height(this.$el)

    console.log(this.pageHeight)
  },

  data: function () {
    console.log('data referenced')

    return {
      pageHeight: '500px'
    }
  },

  computed: {
    styleScrollArea: function () {
      console.log('styleScrollArea referenced ' + this.pageHeight)
      return {
        backgroundColor: this.pageHeight % 2 === 0 ? 'yellow' : 'green',
        height: this.pageHeight
      }
    }
  },

  methods: {

    onResize (size) {
      this.pageHeight = size.height
      console.log(this.pageHeight)
    }

  }
}
</script>

<style lang="stylus">

.page-background {
  background-color: red;
}

.main {
    background-color: green;
}

.scroll-area {
  background-color: yellow;
}

.scroll-area-content {
  background-color: teal;
}

</style>
