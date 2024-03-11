<template>
  <div id="app">
    <div class="feature-container">
      <FeatureBox v-for="i in 6" :key="i" :id="i" />
    </div>
    <div class="resource-container">
      <ResourceFlow leftText="new" rightText="recycled"/>
      <ResourceFlow leftText="Supplier 1" rightText="Supplier 2"/>
      <ResourceFlow leftText="new" rightText="recycled"/>
    </div>
    <button class="calculate-btn">Calculate</button>
  </div>
</template>

<script>
import FeatureBox from './components/FeatureBox.vue';
import ResourceFlow from './components/ResourceFlow.vue';

export default {
  name: 'App',
  components: {
    FeatureBox,
    ResourceFlow
  }
}
</script>

<style>
#app {
  max-width: 1200px;
  margin: auto;
  padding: 20px;
}
.feature-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.resource-container {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  margin-top: 20px;
}
.calculate-btn {
  display: block;
  width: 100%;
  padding: 10px;
  margin-top: 20px;
  background-color: darkblue;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 18px;
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
  transform: scale(0.7); /* Shrink the button a bit to start */
}

.calculate-btn:hover {
  transform: scale(1); /* Scale back to original size on hover */
}
</style>
