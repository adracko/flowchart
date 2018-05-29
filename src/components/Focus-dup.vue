<template>
  <div class="questions">
    <div class="question">
      <input v-model="catBreed" type="radio" name="cat-breed" id="siamese" value="siamese" checked /><label for="siamese"> Siamese</label>
    </div>
    <div class="question">
      <input v-model="catBreed" type="radio" name="cat-breed" id="persian" value="persian" /><label for="persian"> Persian</label>
    </div>
    <div class="question">
      <input v-model="catBreed" type="radio" name="cat-breed" id="bobtail" value="bobtail" /><label for="bobtail"> Bobtail</label>
    </div>
    <button @click="$emit('submit', { key: 'buyFerret', value: buyFerret })">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      catBreed: "siamese",
      assessEffect: false
    };
  },
  watch: {
    catBreed: function() {
      if (this.catBreed === "bobtail") {
        this.assessEffect = true;
      } else {
        this.assessEffect = false;
      }
    }
  }
};
</script>

<style scoped>
.questions {
  text-align: center;
}

label {
  width: 80px;
  display: inline-block;
  padding-left: 10px;
  text-align: left;
}

button {
  border: 2px solid #444;
  padding: 5px 10px;
  border-radius: 4px;
  font-weight: 600;
  margin-top: 15px;
}
</style>
