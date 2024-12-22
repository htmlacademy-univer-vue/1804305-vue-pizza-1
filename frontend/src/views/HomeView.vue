<template>
    <main class="content">
        <form action="#" method="post">

            <div class="content__wrapper">
                <h1 class="title title--big">Конструктор пиццы</h1>

                <dough-chooser/>

                <diameter-chooser/>

                <ingredients-chooser/>

                <content-pizza/>

            </div>

        </form>
    </main>
</template>

<script setup>
    import DiameterChooser from "@/modules/constructor/DiameterChooser.vue";
    import DoughChooser from "@/modules/constructor/DoughChooser.vue";
    import IngredientsChooser from "@/modules/constructor/IngredientsChooser.vue";
    import ContentPizza from "@/modules/constructor/ContentPizza.vue";
</script>


<style lang="scss" scoped>
    @import '@/assets/scss/fonts.scss';
    @import '@/assets/scss/style.scss';
</style>