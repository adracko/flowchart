<template>
    <div class="intro">
        <p>Are you ready to start a <span>Marketing Campaign</span>?</p>
        <button @click="$emit('submit', { key: 'intro', value: true })">Let's Find Out</button>
    </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style scoped>
.intro {
  text-align: center;
}

p {
  text-align: center;
  font-weight: 300;
  font-size: 24px;
}

span {
  font-weight: 700;
}

button {
  border: 2px solid #444;
  padding: 5px 10px;
  border-radius: 4px;
  font-weight: 600;
}
</style>
