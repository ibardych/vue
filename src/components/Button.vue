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
      console.log("clicked")
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
  }
</style>