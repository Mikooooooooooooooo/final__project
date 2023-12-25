<template>
  <div class="outer-square">
    <div class="inner-square">
      <img
        src="@/assets/email.svg"
        alt="Checkmark Icon"
        class="checkmark-icon"
      />
    </div>
    <div class="text">
      <h3>
        Invoice <br />
        Completed
      </h3>
    </div>
    <div class="number"><h2>3.932</h2></div>
  </div>
</template>

<script>
export default {
  // Add any additional configuration or logic here if needed
};
</script>

<style scoped>
.number {
  margin-left: 20px;
}
.outer-square {
  border: 1px solid black;
  display: flex;
  align-items: center;
  background-color: white;
  width: 220px;
  height: 50px;
  padding: 5px;
}

.inner-square {
  border: 1px solid black;
  width: 50px;
  height: 30px;
  background-color: #ffffff; /* Corrected color value */
  margin-right: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.checkmark-icon {
  width: 15px; /* Adjust icon size as needed */
  height: 15px;
  color: white;
}

.text {
  font-size: 14px; /* Adjust font size as needed */
}

.number {
  font-size: 12px; /* Adjust font size as needed */
}
</style>
