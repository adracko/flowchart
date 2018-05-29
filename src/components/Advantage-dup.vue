<template>
  <div class="questions">
    <div class="question">
      <input v-model="dogBreed" type="radio" name="dog-breed" id="pug" value="pug" checked /><label for="pug"> Pug</label>
    </div>
    <div class="question">
      <input v-model="dogBreed" type="radio" name="dog-breed" id="poodle" value="poodle" /><label for="poodle"> Poodle</label>
    </div>
    <div class="question">
      <input v-model="dogBreed" type="radio" name="dog-breed" id="bulldog" value="bulldog" /><label for="bulldog"> Bulldog</label>
    </div>
    <button @click="$emit('submit', { key: 'buyFerret', value: buyFerret })">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dogBreed: "pug",
      assessEffect: true
    };
  },
  watch: {
    dogBreed: function() {
      if (this.dogBreed === "pug") {
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
