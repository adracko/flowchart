<template>
    <div class="questions">
        <p>Focus your marketing.<br>
        What is your Money Maker?</p>
        <div class="question">
            <input v-model="focusMark" type="radio" name="focusMark" id="product" value="product" checked /><label for="product"> A product.</label>
        </div>
        <div class="question">
            <input v-model="focusMark" type="radio" name="focusMark" id="service" value="service" /><label for="service"> A service.</label>
        </div>
        <div class="question">
            <input v-model="focusMarkText" type="text" name="focusMarkText" id="focusMarkText" placeholder="What is the product or service?" />
        </div>
        <button @click="$emit('submit', { key: 'focusMark', value: focusMark } && { key: 'focusMarkText', value: focusMarkText })">Submit</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
        product: "",
        service: "",
      focusMark: "product",
      focusMarkText: ""
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
    width: 110px;
    display: inline-block;
    padding-left: 10px;
    text-align: left;
    font-size: 20px;
    margin-bottom:6px;
}

input[type="text"] {
    height: 30px;
    font-size: 16px;
    width: 400px;
    text-align: center;
    border: 1px solid #ddd;
}

button {
    border: 2px solid #444;
    padding: 5px 10px;
    border-radius: 4px;
    font-weight: 600;
    margin-top: 15px;
}
</style>
