<template>
  <q-page class="column page-content ">

    <q-window-resize-observable @resize="onWindowResize" />
    <q-resize-observable @resize="onPageResize" />

    <q-scroll-area class="col scroll-area">

      <q-resize-observable @resize="onScrollAreaResize" />

      <div v-for="n in 100" :key="n.id" class="scroll-row-content">
        the quick brown fox jumped over the lazy dog
      </div>
    </q-scroll-area>

  </q-page>
</template>

<style>
</style>

<script>

export default {
  name: 'PageIndex',

  methods: {
    onScrollAreaResize (size) {
      console.log('onScrollAreaResize ' + size.height)
    },

    onPageResize (size) {
      console.log('onPageResize ' + size.height)
    },

    onWindowResize (size) {
      console.log('onWindowResize ' + size.height)
    }
  }
}
</script>

<style>

.page-content {
  background-color: green;
}
.scroll-area {
  background-color: red;
}

.scroll-row-content {
  background-color: blue;
  color: white;
}

</style>
