<template>
  <q-page class="column page-content ">

    <q-scroll-area :class="classScrollArea">
      <div v-for="n in 100" :key="n.id" class="scroll-row-content">
        the quick brown fox jumped over the lazy dog
      </div>
    </q-scroll-area>

    <!-- <q-scroll-area class="col scroll-area">
      <div v-for="n in 100" :key="n.id" class="scroll-row-content">
        the quick brown fox jumped over the lazy dog
      </div>
    </q-scroll-area> -->

  </q-page>
</template>

<style>
</style>

<script>

export default {
  name: 'PageIndex',

  computed: {
    classScrollArea: function () {
      return { 'background-color': 'yellow' }
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
