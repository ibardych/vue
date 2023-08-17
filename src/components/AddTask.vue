<template>
  <form @submit="onSubmit">
    <div>
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add task">
    </div>
    <div>
      <label>Day & Time</label>
      <input type="text" v-model="day" name="day" placeholder="Add Day & Time">
    </div>
    <div>
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder">
    </div>

    <input type="submit" value="Save Task">
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      text: '',
      day: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if(!this.text) {
        alert('Please add a task');
      }

      const newTask = {
        id: Math.floor(Math.random() * 100000),
        text: this.text,
        day: this.day,
        reminder: this.reminder
      }

      this.$emit('add-task', newTask);

      this.text = '';
      this.day = '';
      this.reminder = false;
    }
  }
}
</script>

<style scoped lang="scss">
  form {
    display: flex;
    flex-direction: column;
    width: 250px;
    max-width: 100%;
    margin: 0 auto;
    margin-top: 20px;
    padding: 20px;
    box-sizing: border-box;
    border-radius: 10px;
    gap: 12px; 
    background-color: rgba(255,255,255,0.1);

    & div {
      display: flex;
      flex-direction: column;
      gap: 3px;
    }

    & label {
      color: #f5f5f5;
      font-size: 15px;
    }

    & input[type=text] {
      background-color: rgba(255,255,255,0.1);
      border: none;
      padding: 5px 10px;
      border-radius: 3px;
      color: #fff;

      &::placeholder {
        color: #a6a6a6;
      }
    }

    & input[type=submit] {
      background-color: #67d500;
      border: none;
      padding: 10px 20px;
      border-radius: 3px;
      cursor: pointer;
      box-shadow: 0px 1px 3px 0px rgba(0,0,0,0.5), inset 0px 0px 8px 0px rgba(255,255,255,0.3);
      font-weight: 600;

      &:hover {
        opacity: 0.8;
      }
    }
  }
</style>