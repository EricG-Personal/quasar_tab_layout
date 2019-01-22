<template>
  <q-page class="column no-wrap" :style="stylePage">

    <q-resize-observable @resize="onPageResize" />
    <q-window-resize-observable @resize="onWindowResize" />

    <div class="header-content" ref="headerContent">
      page header content
    </div>

    <div class="main">
      <div style="overflow-y: auto">
        <div>
          top
        </div>
        <div v-for="x in 100" :key="x.id" >
          some content
        </div>
        <div>
          bottom
        </div>
      </div>
    </div>

    <div class="footer-content">
      page footer content
    </div>

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
    console.log(this.$el.style.minHeight)

    this.pageHeight = height(this.$el)
    this.$el.style.maxHeight = this.$el.style.minHeight

    // console.log(this.$refs)
  },

  beforeUpdate: function () {
    console.log('beforeUpdate')
    // hello
    // console.log(this.$refs)
  },

  computed: {
    stylePage: function () {
      console.log('styleScrollArea referenced ')
      // console.log(height(this.$el))

      return {
        backgroundColor: 'blue',
        'overflow-y': 'hidden'
        // 'justify-content': 'flex-end'

      }
    }
  },

  methods: {
    onPageResize (size) {
      console.log('page resized')
    },

    onWindowResize (size) {
      console.log('window resized')
      console.log(this.$el.style.minHeight)
    }
  }
}

</script>

<style>

.main {
  flex-grow: 1;
  background-color: green;
  overflow-y: auto;
}

.header-content, .main, .footer-content {
  flex-shrink: 0;
}

/* .page-content {
  background-color: lightgray;

  min-height: 100%;
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.main {
  flex-grow: 1;
  background-color: green;
}

.title-content, .main, .key-content {
  flex-shrink: 0;
}

.scroll-area {
  width: 100%;
  height: 100px;
  background-color: yellow;
} */

</style>
