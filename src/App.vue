<template>
    <div id="app">
        <v1-grid flat size="14x10" gap="0">
            <v1-cell borderBottom size="14x1">
                <v1-nav />
            </v1-cell>
            <v1-cell border middle size="6x4" y="3" x="4">
                <div class="flowchart">
                    <Intro v-if="!intro" v-on:submit="onSubmit" />
                    <Identify v-if="intro && !marketOpp" v-on:submit="onSubmit" />
                    <Focus v-if="assessEffect === null && marketOpp == 'focus'" v-on:submit="onSubmit" />
                    <Advantage v-if="assessEffect === null && marketOpp == 'advantage'" v-on:submit="onSubmit" />
                    <Conclusion v-if="assessEffect !== null" :assessEffect="assessEffect" />
                </div>
            </v1-cell>
            <v1-cell border middle size="2x4" y="3" x="11">
                <div class="answers">
                    <p v-if="focusMarkText !== ''">Product or Service:<br>{{ focusMarkText }}</p>
                </div>
            </v1-cell>
            <v1-cell borderTop size="14x1" y="9">
                <v1-footer />
            </v1-cell>
        </v1-grid>
    </div>
</template>

<script>
import Identify from "./components/Identify";
import Focus from "./components/Focus";
import Advantage from "./components/Advantage";
import Intro from "./components/Intro";
import Conclusion from "./components/Conclusion";

export default {
  name: "App",
  data() {
    return {
      marketOpp: null,
      assessEffect: null,
      focusMark: null,
      focusMarkText: "",
      intro: null
    };
  },
  components: {
    Identify,
    Focus,
    Advantage,
    Intro,
    Conclusion
  },
  methods: {
    onSubmit: function(q) {
      this[q.key] = q.value;
    }
  }
};
</script>

<style>
*:focus {
  outline: none;
}

body {
  padding: 0;
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.flowchart {
  color: #444;
  width: 100%;
}

.flat .cell {
    overflow:hidden !important;
}
</style>
