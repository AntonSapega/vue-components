<template>
  <div class="input-class">
    <form>
      <label for="unit">Еденица</label>
      <input type="text" id="unit" v-bind:value="selectedValue" v-on:focus="inputInFocus" v-on:blur="inputLoseFocus" v-bind:placeholder="changePlaceholder"/>

      <ul v-bind:class="showList">
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem($event)">{{unit[0]}}</li>
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem">{{unit[1]}}</li>
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem">{{unit[2]}}</li>
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem">{{unit[3]}}</li>
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem">{{unit[4]}}</li>
        <li v-on:mouseover="hoverOnUnit" v-on:click="clickedElem">{{unit[5]}}</li>
      </ul>
    </form>
    <!-- <button type="button" v-on:click="clickedElem">Click</button> Just for example that event "onclick" realy work -->
  </div>
</template>



<script>
export default {
  data(param) {
    return {
      unit: ["kg", "lit", "gr", "mm", "cm", "dc"],
      selectedValue: '',
      inFocus: false,
      showList: "hidden",
      changePlaceholder: "Enter  unit"
    };
  },
  methods: {
    inputInFocus() {
      this.inFocus = true;
      this.showList = "visible";
      this.changePlaceholder = '';
    },
    inputLoseFocus() {
      this.showList = "hidden";
      this.changePlaceholder = 'Enter  unit';
    },
    hoverOnUnit(event) {
      this.changePlaceholder = event.toElement.innerHTML;
      // this.selectedValue = event.toElement.innerHTML;

    },
    clickedElem(event) {
      
      console.log(event.bubbles);
    }
  }
};
</script>



<style>
/* СБРОС СТИЛЕЙ */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/* Убираем внутренние отступы */
ul[class],
ol[class] {
  padding: 0;
}

/* Убираем внешние отступы */
body,
h1,
h2,
h3,
h4,
p,
ul[class],
ol[class],
li,
figure,
figcaption,
blockquote,
dl,
dd {
  margin: 0;
}

/* Выставляем основные настройки по-умолчанию для body */
body {
  min-height: 100vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
}

/* Удаляем стандартную стилизацию для всех ul и il, у которых есть атрибут class*/
ul[class],
ol[class] {
  list-style: none;
}

/* Элементы a, у которых нет класса, сбрасываем до дефолтных стилей */
a:not([class]) {
  text-decoration-skip-ink: auto;
}

/* Упрощаем работу с изображениями */
img {
  max-width: 100%;
  display: block;
}

/* Указываем понятную периодичность в потоке данных у article*/
article > * + * {
  margin-top: 1em;
}

/* Наследуем шрифты для инпутов и кнопок */
input,
button,
textarea,
select {
  font: inherit;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  letter-spacing: 2px;
  color: rgb(90, 90, 90);
}

.input-class {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: rgb(240, 238, 238);
}

form {
  position: relative;
}

label {
  margin: 0 0 5px 5px;
  font-size: 18px;
}

input {
  border: 1px solid rgb(240, 238, 238);
  padding: 0 0 0 10px;
  display: block;
  width: 250px;
  height: 40px;
  font-size: 16px;
  border-width: 1px;
}

input:focus,
input:active {
  /* outline: none;
	box-shadow: none; */
  /* border-width: 1px;*/
  border-color: #80bdff;
  /* box-sizing: border-box; */
  outline: 0;
  outline-offset: -1px;
  /* width: 250px;
	height: 40px; */
}

ul {
  list-style-type: none;
  width: 250px;
  background-color: white;
  margin: 0px;
  padding: 0 0 0 0;
  display: block;
  position: absolute;
  top: 67px;
}

.hidden {
  display: none;
}

.visible {
  display: block;
}

li {
  padding-left: 10px;
}

ul li:hover {
  background-color: #80bdff;
  cursor: pointer;
}
</style>