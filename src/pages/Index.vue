<template>
  <q-page class="column no-wrap" :style="stylePage">

    <!-- <q-resize-observable @resize="onPageResize" />
    <q-window-resize-observable @resize="onWindowResize" /> -->

    <div class="sticky-top" ref="headerContent">
      page header content
    </div>

    <div class="sticky-bottom">
      page footer content
    </div>

    <div :style="scrollStyle">
      <div v-for="x in 100" :key="x" >
        some content
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',

  mounted: function () {
    console.log('is mounted')
  },

  beforeUpdate: function () {
    console.log('beforeUpdate')
  },

  computed: {
    scrollStyle: function () {
      return {
        position: 'fixed',
        // 50 + 59
        top: '109px',
        width: '100%',
        // 40 + 59
        bottom: '99px',
        overflow: 'auto'
      }
    }
  },

  watch: {
  },

  methods: {
  }
}

</script>

<style>
div.sticky-top {
  position: fixed;
  top: 50px;
  width: 100%;
  background-color: yellow;
  padding: 20px;
  font-size: 16px;
}

div.sticky-bottom {
  position: fixed;
  bottom: 42px;
  width: 100%;
  background-color: yellow;
  padding: 20px;
  font-size: 16px;
}

.main {
  flex-grow: 1;
  background-color: green;
  overflow-y: auto;
}

/* .header-content, .main, .footer-content {
  flex-shrink: 0;
} */

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
