<template>
  <main>
    <div class="container">
        <label for="multi">MultiAddr</label>
        <input id="multi" type="text" ref="multi" v-model="multi" @change="onMultiAddrInput" />
        <Tooltip :text="multiTooltip" />
    </div>
    <div class="container">
        <label for="uri">Uri</label>
        <input id="uri" type="text" ref="uri" v-model="uri" @change="onUriAddrInput" />
        <Tooltip :text="uriTooltip" />
    </div>
  </main>
</template>

<script>
import multiToUri from "multiaddr-to-uri";
import uriToMulti from "uri-to-multiaddr";

import Tooltip from './Tooltip.vue';

export default {
  components: {
    Tooltip
  },
  data: () => ({ multi: '', uri: '', multiTooltip: null, uriTooltip: null}),
  methods: {
    onMultiAddrInput(ev) {
      this.multiTooltip = null;

      try {
        const uriResult = multiToUri(this.multi)
        this.multiTooltip = null;

        this.uri = uriResult
      }
      catch(e) {
        console.error(e)
        this.multiTooltip = e.message
      }
    },
    onUriAddrInput() {
      this.uriTooltip = null;

      try {
        const multiResult = uriToMulti(this.uri)
        this.uriTooltip = null;

        this.multi = multiResult
      }
      catch(e) {
        console.error(e)
        this.uriTooltip = e.message
      }
    },
  },
};
</script>

<style scoped>
main {
  display: flex;
  height: 100vh;
  width: 100vw;
  justify-content: center;
  align-items: center;
}

.container {
  position: relative;
  margin: 0 3vw;
}

label {
  font-size: 1.4rem;
}
</style>