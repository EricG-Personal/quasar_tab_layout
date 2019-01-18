<template>
  <q-page class="page-content">

    <q-resize-observable @resize="onPageResize" />
    <q-window-resize-observable @resize="onWindowResize" />

    <div class="title-content">
      branding content
    </div>

    <q-tabs animated swipeable color="tertiary" glossy align="left">

      <q-tab default name="list" slot="title" label="List" />
      <q-tab name="category" slot="title" label="Category" />

      <q-tab-pane keep-alive name="list">
<!--
        <q-scroll-area style="width: 400px; max-width: 85vw; height: 470px; max-height: 70vh;">
          <div v-for="n in 100" :key="n.id">
            Lorem ipsum dolor sit amet, consectetur adipisicing
            elit, sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua.
          </div>
        </q-scroll-area> -->

        <div v-for="n in 100" :key="n.id">
          the quick brown fox jumped over the lazy dog
        </div>

        <!-- <q-scroll-area class="fill-area">
          <div v-for="n in 10">
            Lorem ipsum dolor sit amet, consectetur adipisicing
            elit, sed do eiusmod tempor incididunt ut labore et
            dolore magna aliqua.
          </div>
        </q-scroll-area> -->

          <!-- <q-scroll-area class="appScrollArea">
            <div class="row">
              <div v-for="cardDatum in cardData( 'all' )" :key="cardDatum.id" class="cardItem">
                <AppInfoCard :info="cardDatum" />
              </div>
            </div>
          </q-scroll-area> -->

      </q-tab-pane>

    </q-tabs>

    <!-- <div class="main">
      <div v-for="n in 100" :key="n.id">
          the quick brown fox jumped over the lazy dog
      </div>
    </div> -->

    <!-- <div>
      branding content
    </div>

    <div>
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
    </div> -->
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
} */

</style>
