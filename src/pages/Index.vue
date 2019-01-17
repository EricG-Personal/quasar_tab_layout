<template>
  <q-page class="column page-content ">

    <!-- <q-scroll-area :class="classScrollArea">
      <div v-for="n in 100" :key="n.id" class="scroll-row-content">
        the quick brown fox jumped over the lazy dog
      </div>
    </q-scroll-area> -->

    <q-scroll-area :style="styleScrollArea" ref="a">
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

// import { dom } from 'quasar'
// const { height, width } = dom

export default {
  name: 'PageIndex',

  computed: {
    styleScrollArea: function () {
      // console.log(
      //   height(this.$refs.a),
      //   width(this.$refs.a)
      // )

      return {
        // 'height': '50vh',
        'height': 'calc(100vh - 25vh)',
        'background-color': 'yellow'
      }
    },

    classScrollArea: function () {
      return 'scroll-area'
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
  height: calc(100vh - 25vh);
}

.scroll-row-content {
  background-color: blue;
  color: white;
}

</style>
