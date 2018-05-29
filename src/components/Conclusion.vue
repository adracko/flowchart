<template>
  <div class="conclusion">
    <p>You <span>{{message()}}</span> buy a ferret!</p>
  </div>
</template>

<script>
export default {
  props: {
    buyFerret: Boolean
  },
  data() {
    return {};
  },
  methods: {
    message: function() {
      if (this.buyFerret === true) {
        return "SHOULD";
      } else {
        return "SHOULD NOT";
      }
    }
  }
};
</script>

<style scoped>
.conclusion {
  text-align: center;
  font-weight: 300;
  font-size: 24px;
}

span {
  font-weight: 700;
}
</style>
