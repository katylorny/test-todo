<template>
  <li class="todo-item">
    <label class="todo-item__label">
      <input class="todo-item__checkbox" disabled type="checkbox" :checked="todoItem.checked">
      <span> {{ todoItem.text }} </span>
    </label>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todoItem: {
      type: Object
    }
  },
  mounted() {
    // console.log(this.todoItem);
  }
}
</script>

<style lang="scss" scoped>

.todo-item {
  list-style: none;


  label {
    display: flex;
    justify-content: start;
  }


  span {
    text-align: left;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    display: block;
    padding-left: 23px;
    opacity: 0.9;
  }

  p {
    margin-top: 0;
    margin-bottom: 10px;
  }
}

.todo-item__label {

}

.todo-item__checkbox {
  display: none;
}

.todo-item__checkbox:not(:checked) + span {
  position: relative;

  &::before {
    opacity: 0.4;
    position: absolute;
    content: "";
    top: calc(50% - 7px);
    left: 0;
    height: 13px;
    width: 13px;
    border: 1px solid black;
    border-radius: 2px;
  }
}

.todo-item__checkbox:checked + span {
  position: relative;

  &::before {
    opacity: 0.4;
    background: url("../assets/icon-checkbox.png") no-repeat;
    position: absolute;
    content: "";
    top: calc(50% - 6px);
    left: 0;
    height: 15px;
    width: 15px;
    background-size: cover;
    border: none;
  }
}
</style>