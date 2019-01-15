<template>
  <q-page class="page-content">

    <div class="title-content">
      title content
    </div>

    <div class="main">
      <q-tabs animated swipable color="tertiary" glossy align="left">

        <q-tab default name="taba" slot="title" label="TabA" />
        <q-tab name="tabb" slot="title" label="TabB" />

        <q-tab-pane keep-alive name="taba">
          <q-scroll-area class="scroll-area">
            <div v-for="n in 100" :key="n.id">
              the quick brown fox jumped over the lazy dog
            </div>
          </q-scroll-area>
        </q-tab-pane>

        <q-tab-pane keep-alive name="tabb">
          <div>tab b content</div>
        </q-tab-pane>

      </q-tabs>
    </div>

    <div class="key-content">
      key content
    </div>
  </q-page>
</template>

<style>
</style>

<script>

import {
  QTabs,
  QTab,
  QTabPane,
  QScrollArea
} from 'quasar'

export default {
  name: 'PageIndex',

  components: {
    QTabs,
    QTab,
    QTabPane,
    QScrollArea
  }
}
</script>

<style>

.page-content {
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
}
</style>
