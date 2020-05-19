<template>
  <div class="input-class">
    <input type="text" placeholder="size" />
		<ul>
			<li>kg</li>
			<li>cm</li>
			<li>lit</li>
			<li>gr</li>
		</ul>
  </div>
</template>

<script>
export default {

};
</script>

<style>

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


.input-class {
  display: flex;
	flex-direction: column;
  justify-content: center;
  align-items: center;
	height: 100vh;
	background-color: whitesmoke;
}

input {
	padding: 0 0 0 10px;
  display: block;
	width: 250px;
	height: 40px;
	font-size: 16px;
	border-width: 0px;
}

input:focus, input:active {
	outline: none;
	box-shadow: none;
	border-width: 1px;
	border-color: #80bdff;
}

ul {
	list-style-type: none;
	width: 250px;
	background-color: white;
	margin: 0px;
	padding: 0 0 0 10px;
	display: block;
}

ul li:hover {
	background-color: #80bdff;
	cursor: pointer;
}
</style>