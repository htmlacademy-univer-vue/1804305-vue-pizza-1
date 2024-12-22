<template>
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
</template>

<script setup>
    import ingredients from '@/mocks/ingredients.json';
    import sauces from "@/mocks/sauces.json";

    const str = "filling/mushrooms.svg";
    const parts = str.split('/');
    const fileName = parts[1].slice(0, parts[1].lastIndexOf('.'));
</script>

<style lang="scss" scoped>
    @import '@/assets/scss/fonts.scss';
    @import '@/assets/scss/style.scss';
</style>