<template>
  <button @click="onClick()" :style="{backgroundColor: color}" class="btn">{{ text }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String
  },
  methods: {
    onClick() {
      this.$emit('toggle-add-task');
    }
  }
}
</script>

<style scoped lang="scss">
  .btn {
    color: #fff;
    border: none;
    border-radius: 3px;
    padding: 10px 20px;
    cursor: pointer;
    box-shadow: 0px 1px 3px 0px rgba(0,0,0,0.5), inset 0px 0px 8px 0px rgba(255,255,255,0.3);
    font-weight: 600;

    &:hover {
      opacity: 0.8;
    }
  }
</style>