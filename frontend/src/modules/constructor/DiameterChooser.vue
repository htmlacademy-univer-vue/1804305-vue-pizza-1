<template>
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
</template>

<script setup>
    import sizes from '@/mocks/sizes.json';
    const multiplierSizeMap = { 1: "small", 2: "normal", 3: "big" };

</script>

<style lang="scss" scoped>
    @import '@/assets/scss/fonts.scss';
    @import '@/assets/scss/style.scss';
</style>