<template>
  <div class="note">
    <div class="header" :style='{ backgroundImage: `url("${backgroundImg}")` }'>
      <div class="buttons">
        <button class="options-button">
          <img :src="editButtonImg2" alt="Редактировать">
        </button>
        <button class="options-button">
          <img :src="deleteButtonImg2" alt="Удалить">
        </button>
      </div>
      <h3>{{ title }}</h3>
    </div>
    <div class="main">
      <ul v-if="todoItems.length >= 1">
        <todo-item v-for="(todoItem, i) in todoItems.slice(0, 4)" :key="i" :todo-item="todoItem"/>
      </ul>
      <div v-else>
        <p>
          Тут ничего нет
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import sunsetImg from "@/assets/sunset.jpg"
import deleteButtonImg from "@/assets/icon-delete.png"
import deleteButtonImg2 from "@/assets/Icon-delete2.png"
import editButtonImg from "@/assets/icon-edit.png"
import editButtonImg2 from "@/assets/icon-edit2.png"
import TodoItem from "@/components/TodoItem";


export default {
  name: 'Note',
  components: {TodoItem},
  props: {
    backgroundImg: {
      type: String,
      default: sunsetImg,
    },
    title: {
      type: String,
    },
    todoItems: {
      type: Array
    }
  },
  data() {
    return {
      sunsetImg,
      deleteButtonImg,
      deleteButtonImg2,
      editButtonImg,
      editButtonImg2
    }
  }
}

</script>

<style lang="scss" scoped>
.note {
  word-break: normal;
  tab-size: 4;
  font-size: 16px;
  font-family: Roboto, sans-serif;
  line-height: 1.5;
  display: block;
  text-decoration: none;
  white-space: normal;
  border-color: #fff;
  background-color: #fff;
  color: rgba(0, 0, 0, .87);
  border-radius: 4px;
  box-shadow: 0 3px 7px 0px rgba(0, 0, 0, .2), 0 3px 3px 0 rgba(0, 0, 0, .14), 0 2px 8px 0 rgba(0, 0, 0, .12);

  margin: 10px;
  padding: 0;
  width: 300px;
  height: 300px;
  overflow: hidden;

  h2, p {
    color: black;
    text-align: left;
    margin-top: 0;
    margin-bottom: 10px;
  }

  h3 {
    margin-top: auto;
    margin-bottom: 0;
    color: white;
    width: 100%;
    padding: 10px;
    background: rgba(7, 7, 7, 0.54);
    text-align: left;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }


}

.header {
  height: 62%;
  overflow: hidden;
  background-size: cover;
  display: flex;
  flex-direction: column;
}

.main {
  padding: 10px;

  ul {
    padding: 0;
    margin: 0;
  }

}

.buttons {
  margin-left: auto;
  margin-top: 10px;
  display: flex;
}

.options-button {
  width: 30px;
  height: 30px;
  background: white;
  border: none;
  padding: 5px;
  border-radius: 50%;
  margin-right: 10px;
  cursor: pointer;
  display: flex;
  transition: all 0.1s ease;
  box-shadow: 0 3px 7px 0px rgba(0, 0, 0, .2), 0 3px 3px 0 rgba(0, 0, 0, .14), 0 2px 8px 0 rgba(0, 0, 0, .12);


  &:hover {
    transform: scale(1.2);
  }

  img {
    display: block;
    width: 87%;
    margin: auto;
  }
}
</style>