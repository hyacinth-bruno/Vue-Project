<template>
  <div class="feature-box">
    <h3>Feature</h3>
    <div class="options">
      <label v-for="(option, index) in options" :key="index" class="option">
        <!-- Bind the radio button name to ensure each set of options is grouped -->
        <input type="radio" :name="`feature-${id}`" :value="option" v-model="selectedOption">
        <span class="custom-radio"></span>
        {{ option }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeatureBox',
  props: {
    id: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      options: ['Option A', 'Option B', 'Option C'],
      selectedOption: null
    };
  },
};
</script>

<style scoped>
.feature-box {
  background-color: lightblue;
  border: 3px solid darkblue;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  width: calc(30% - 20px);
  box-sizing: border-box;
}

h3 {
  color: darkblue;
  margin-bottom: 15px;
}

.options {
  display: flex;
  flex-direction: column;
}

.option {
  margin-bottom: 5px;
  display: flex;
  align-items: center;
}

/* Custom radio button style */
.custom-radio {
  display: inline-block;
  margin-right: 10px;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  border: 2px solid #000;
  position: relative;
}

/* When the radio button is checked, add a blue background */
.custom-radio::after {
  content: '';
  display: none;
  position: absolute;
  top: 3px;
  left: 3px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: darkblue;
}

.option input[type="radio"]:checked + .custom-radio::after {
  display: block;
}

/* Hide the default radio button */
.option input[type="radio"] {
  opacity: 0;
  position: absolute;
  width: 0;
  height: 0;
  margin: 0;
}
</style>
