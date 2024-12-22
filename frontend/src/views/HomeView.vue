<template>
    <main class="content">
        <form action="#" method="post">

            <div class="content__wrapper">
                <h1 class="title title--big">Конструктор пиццы</h1>

                <div class="content__dough">
                    <div class="sheet">
                        <h2 class="title title--small sheet__title">Выберите тесто</h2>

                        <div class="sheet__content dough">

                            <label v-for="({ name, description }) in dough" class="dough__input"
                                :class="{ 'dough__input--light': name === 'Тонкое', 'dough__input--large': name === 'Толстое' }">
                                <input type="radio" name="dought" value="light" class="visually-hidden" checked>
                                <b>{{ name }}</b>
                                <span>{{ description }}</span>
                            </label>
                        </div>
                    </div>
                </div>

                <div class="content__diameter">
                    <div class="sheet">
                        <h2 class="title title--small sheet__title">Выберите размер</h2>

                        <div class="sheet__content diameter">
                            <label v-for="({ name, multiplier }) in sizes" class="diameter__input"
                                :class="`diameter__input--${multiplierSizeMap[multiplier]}`">
                                <input type="radio" name="diameter" :value="multiplierSizeMap[multiplier]"
                                    class="visually-hidden">
                                <span>{{ name }}</span>

                            </label>
                        </div>
                    </div>
                </div>

                <div class="content__ingredients">
                    <div class="sheet">
                        <h2 class="title title--small sheet__title">Выберите ингредиенты</h2>

                        <div class="sheet__content ingredients">

                            <div class="ingredients__sauce">
                                <p>Основной соус:</p>      
                                <label v-for="sauce in sauces" :key="sauce.id" 
                                    class="radio ingredients__input">
                                    <input type="radio" 
                                    name="sauce" 
                                    :value="sauce.name"
                                    :checked="sauce.id === 1" 
                                     />
                                    <span>{{ sauce.name }}</span>
                                </label>
                            </div>

                            <div class="ingredients__filling">
                                <p>Начинка:</p>

                                <ul class="ingredients__list">
                                    <li v-for="({name}) in ingredients" class="ingredients__item">
                                        <span class="filling">{{ name }}</span>
                                        <div class="counter counter--orange ingredients__counter">
                                            <button type="button" class="counter__button counter__button--minus"
                                                disabled>
                                                <span class="visually-hidden">Меньше</span>
                                            </button>
                                            <input type="text" name="counter" class="counter__input" value="0">
                                            <button type="button" class="counter__button counter__button--plus">
                                                <span class="visually-hidden">Больше</span>
                                            </button>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="content__pizza">
                    <label class="input">
                        <span class="visually-hidden">Название пиццы</span>
                        <input type="text" name="pizza_name" placeholder="Введите название пиццы">
                    </label>

                    <div class="content__constructor">
                        <div class="pizza pizza--foundation--big-tomato">
                            <div class="pizza__wrapper">
                                <div class="pizza__filling pizza__filling--ananas"></div>
                                <div class="pizza__filling pizza__filling--bacon"></div>
                                <div class="pizza__filling pizza__filling--cheddar"></div>
                            </div>
                        </div>
                    </div>

                    <div class="content__result">
                        <p>Итого: 0 ₽</p>
                        <button type="button" class="button" disabled>Готовьте!</button>
                    </div>
                </div>

            </div>

        </form>
    </main>
</template>

<script setup>
import sauces from "../mocks/sauces.json";
import dough from '../mocks/dough.json';
import sizes from '../mocks/sizes.json';
import ingredients from '../mocks/ingredients.json';

const multiplierSizeMap = { 1: "small", 2: "normal", 3: "big" };


const str = "filling/mushrooms.svg";
const parts = str.split('/');
const fileName = parts[1].slice(0, parts[1].lastIndexOf('.'));
</script>


<style lang="scss" scoped>
    @import '@/assets/scss/fonts.scss';
    @import '@/assets/scss/style.scss';
</style>