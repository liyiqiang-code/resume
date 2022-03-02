<template>
  <div class="header">
    <div class="introduce_header"><slot></slot></div>
    <div class="line"></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: start;
  align-items: center;
  margin-bottom: 10px;
  margin-top: 10px;
}

.introduce_header {
  font-weight: 900;
  font-size: 20px;
  flex: 1;
}

.line {
  border-bottom: 2px dashed #000;
  height: 1px;
  flex: 9;
}
</style>
