<template>
  <div class="associated">
    <p class="associated-title">Связанные профили</p>
    <div class="associated-people">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
      <img src="../assets/avatar-small.svg">
    </div>
    <div class="associated-nav">
      <b-icon class="button-chevron" icon="chevron-left"></b-icon>
      <svg id="annotation" width="48" height="16">
        <circle cx="8" cy="8" r="4" fill="#BDBDC7"/>
        <circle cx="24" cy="8" r="4" fill="#4E8EF8"/>
        <circle cx="40" cy="8" r="4" fill="#BDBDC7"/>
      </svg>
      <b-icon class="button-chevron" icon="chevron-right"></b-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Associated',
}
</script>

<style scoped>
.associated {
  margin-top: 24px;
  margin-left: 8px;
}

.associated-title {
  font-size: 16px;
  font-weight: 600;
}

.associated-people {
  display: flex;
  padding-left: 18px;
  padding-right: 29px;
  flex-direction: row;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  border-radius: 7px;
  justify-content: space-around;
  align-items: center;
  width: 375px;
  height: 86px;
}

.associated-nav {
  margin-top: 16px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.associated-nav circle {
  cursor: pointer;
}

.button-chevron {
  color: #4E8EF8;
  width: 20px;
  height: 20px;
  cursor: pointer;
}
</style>
