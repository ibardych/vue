<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <div class="text">
      {{ task.text }}
    </div>
    <div class="day">{{ task.day }}</div>
    <i @click="onDelete(task.id)" class="fas fa-times delete"></i>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object
  },
  methods: {
    onDelete(id) {
      this.$emit('delete-task', id)
    }
  }
}
</script>

<style scoped lang="scss">
  .task {
    background-color: rgba(255,255,255,0.2);
    border-radius: 5px;
    box-shadow: 0px 1px 3px 0px rgba(0,0,0,0.5);
    width: 200px;
    max-width: 100%;
    padding: 10px 18px;
    position: relative;
    overflow: hidden;

    &.reminder::after {
      content: "";
      display: block;
      width: 3px;
      height: 100%;
      background-color: greenyellow;
      position: absolute;
      left: 0px;
      top: 0px;
    }
  }
  .text {
    font-size: 16px;
    line-height: 1.4;
    color: #f5f5f5;
    margin-bottom: 5px;
    font-weight: 500;
    text-align: left;
  }
  .day {
    font-size: 14px;
    line-height: 1;
    color: #999999;
    text-align: left;
  }
  .delete {
    color: #fff;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    right: 10px;
    cursor: pointer;

    &:hover {
      opacity: 0.8;
    }
  }
</style>