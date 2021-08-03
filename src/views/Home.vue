<template>
  <div class="home">
    <Header/>
    <div class="notes">
      <note v-for="(note, i) in notes" :key="i" :background-img="note.img" :title="note.title"
            :todo-items="note.todos"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Note from "@/views/Note";
import sunsetImg from "@/assets/sunset.jpg";
import funchosaImg from "@/assets/funchoza.jpg";
import kittyImg from "@/assets/kitty.png";
import newYearImg from "@/assets/newyear.jpg";

import Header from "@/components/Header";


export default {
  name: 'Home',
  components: {
    Header,
    Note,
  },
  data() {
    return {
      sunsetImg,
      funchosaImg,
      kittyImg,
      newYearImg,
      notes: [
        {
          title: 'Рецепт фунчозы',
          todos: [
            {
              text: "фунчоза",
              checked: false,
            },
            {
              text: "красный сладкий перец",
              checked: false,
            },
            {
              text: "желтый сладкий перец",
              checked: false,
            },
            {
              text: "соль и перец по вкусу",
              checked: false,
            },
          ],
          img: funchosaImg
        },
        {
          title: 'Планы на сегодня',
          img: kittyImg,
          todos: [
            {
              text: "поесть",
              checked: false,
            },
            {
              text: "поспать",
              checked: false,
            },
            {
              text: "покормить голодного котика, иначе котик будет воровать еду",
              checked: true,
            },
            {
              text: "поработать",
              checked: false,
            },
          ]
        },
        {
          title: 'Подарки на нг для моих сладких',
          img: newYearImg,
          todos: [
            {
              text: "мама",
              checked: true,
            },
            {
              text: "котик",
              checked: true,
            },
            {
              text: "Лиза",
              checked: false,
            },
          ]
        },
        {
          title: 'Заметка 4',
          todos: []
        },
        {
          title: 'Заметка 5',
          todos: []
        },
        {
          title: 'Заметка 6',
          todos: []
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

.notes {
  display: flex;
  flex-wrap: wrap;
}

</style>