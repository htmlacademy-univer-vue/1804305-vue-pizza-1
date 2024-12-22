<template>
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
</template>

<script setup>
    import dough from '@/mocks/dough.json';
</script>

<style lang="scss" scoped>
    @import '@/assets/scss/fonts.scss';
    @import '@/assets/scss/style.scss';
</style>