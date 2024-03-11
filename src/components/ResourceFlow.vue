<template>
  <div class="resource-flow">
    <div class="content new">
      <span>{{ leftText }}</span>
    </div>
    <div class="content recycled">
      <span class="arrow">→</span>
      <span>{{ rightText }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ResourceFlow',
  props: {
    leftText: String,
    rightText: String
  }
};
</script>

<style scoped>
.resource-flow {
  display: flex;
  border: 2px solid rgb(70, 151, 218);
  border-radius: 10px;
  overflow: hidden; /* Keeps the child divs' border-radius within the parent */
  margin: 10px;
  width: 100%;
}

.resource-flow .content {
  padding: 10px;
  width: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.new {
  background-color: darkblue;
  color: white;
}

.recycled {
  background-color: lightblue;
  color: black;
  position: relative;
}

.arrow {
  font-size: 24px;
  font-weight: bold; /* Makes the arrow bold */
  margin: 0 20px;
}

/* Adds a separator line */
.recycled::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  border-left: 2px solid black;
}
</style>
