<template>
  <div class="button-group">
    <button class="" :disabled="leftButtonDisabled" @click="leftButtonClick">
      &lt;
    </button>
    <button class="" :disabled="rightButtonDisabled" @click="rightButtonClick">
      &gt;
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  leftButtonDisabled: {
    type: Boolean,
    default: true
  },
  rightButtonDisabled: {
    type: Boolean,
    default: true
  }
})
const emit = defineEmits(["leftButtonClick", "rightButtonClick"])
const leftButtonClick = () => {
  emit("leftButtonClick")
}
const rightButtonClick = () => {
  emit("rightButtonClick")
}
</script>
<style lang="scss" scoped>
.button-group {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  border-left: 1px solid #ddd;
  border-right: 1px solid #ddd;
  button {
    border: none;
    outline: none;
    width: 38px;
    height: 38px;
    background-color: orange;
    color: white;
    border-radius: 5px;
    &:disabled {
      opacity: 0.6;
    }
    &:nth-child(2) {
      margin-left: 10px;
    }
  }
}
</style>
