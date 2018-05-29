<template>
    <div class="questions">
        <p>Identify a Market Opportunity.</p>
        <div class="question">
            <input v-model="marketOpp" type="radio" name="marketOpp" id="focus" value="focus" checked /><label for="focus"> To focus you marketing.</label>
        </div>
        <div class="question">
            <input v-model="marketOpp" type="radio" name="marketOpp" id="advantage" value="advantage" /><label for="advantage"> To create a competitive advantage.</label>
        </div>
        <div class="question">
            <input v-model="marketOpp" type="radio" name="marketOpp" id="demand" value="demand" /><label for="demand"> To meet a market demand.</label>
        </div>
        <div class="question">
            <input v-model="marketOpp" type="radio" name="marketOpp" id="questions" value="questions" /><label for="questions"> To answer marketing questions.</label>
        </div>
        <button @click="$emit('submit', { key: 'marketOpp', value: marketOpp })">Submit</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      marketOpp: "focus"
    };
  }
};
</script>

<style scoped>
.questions {
  text-align: center;
}

p {
    text-align: center;
    font-weight: 300;
    font-size: 28px;
}

label {
    width: 325px;
    display: inline-block;
    padding-left: 10px;
    text-align: left;
    font-size: 20px;
    margin-bottom:6px;
}

button {
    border: 2px solid #444;
    padding: 5px 10px;
    border-radius: 4px;
    font-weight: 600;
    margin-top: 15px;
}
</style>
