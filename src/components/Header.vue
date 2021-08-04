<template>
  <div class="header">
<!--    <img :src="logoImg" alt="Логотип" width="70">-->
    <button @click="onClick" type="button" class="new-note-button">
      <img :src="addImg" alt="Создать новую заметку">
    </button>
  </div>
</template>

<script>

import logoImg from "@/assets/to-do.png";
import addImg from "@/assets/icon-add.png";

export default {
  name: "Header",
  data() {
    return {
      addImg,
      logoImg,
    }
  },
  methods: {
    onClick() {
      this.$router.push('/note')
    }
  }
}
</script>

<style lang="scss" scoped>

.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
  //background: #c5c5c5;
  padding-top: 20px;
  padding-bottom: 20px;
  padding-left: 4px;
}

.new-note-button {
  background: transparent;
  border: none;
  cursor: pointer;
  align-self: center;
  width: 50px;
  margin-right: 150px;
  transition: all 0.1s ease;

  &:hover {
    transform: scale(1.2);
  }

  img {
    object-fit: cover;
    width: 100%;
    height: 100%;
  }
}
</style>