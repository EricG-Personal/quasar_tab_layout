<template>
  <q-page class="padding page-content">

    <q-resize-observable @resize="onPageResize" />
    <q-window-resize-observable @resize="onWindowResize" />

    <div>
      <div>
        top
      </div>
      <div v-for="n in 100" :key="n.id">
        the quick brown fox jumped over the lazy dog
      </div>
      <div>
        bottom
      </div>
    </div>

  </q-page>
</template>

<style>
</style>

<script>

export default {
  name: 'PageIndex',

  methods: {
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
  background-color: lightgray;
}

</style>
