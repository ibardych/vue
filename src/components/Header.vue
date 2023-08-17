<template>
  <header>
    <h1>{{title}}</h1>
    <Button text="Add" color="#b80946" />
  </header>
</template>

<script>
import Button from './Button';

export default {
  name: "Header",
  components: {
    Button
  },
  props: {
    title: {
      type: String,
      default: "Hello World"
    }
  }
}
</script>

<style scoped lang="scss">
  header {
    padding: 30px 0;
    background-color: rgba(255,255,255,0.1);
    
    & h1 {
      font-size: 18x;
      color: #f5f5f5;
    }
  }
</style>