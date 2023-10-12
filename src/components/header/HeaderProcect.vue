<template>
    <header class="header">
        <div class="header__logo logo-header">
            <div class="logo-header__img">
                <img src="../../img/header/img-none.png" alt="">
            </div>
            <span class="logo-header__txt">Логотип</span>
        </div>
        <a href="#" class="header__catalog catalog-header">
            <div class="catalog-header__txt">Каталог</div>
        </a>
        <div class="header__search search-header">
            <input
            class="search-header__input" 
            type="text"
            placeholder="Поиск по 100 000 товаров"
            >
            <button class="search-header__btn">Найти</button>
        </div>
        <ul class="header__menu menu-header">
            <li><a class="menu-header__item" href="#">Информация о компании</a></li>
            <li><a class="menu-header__item" href="#">Контакты</a></li>
            <li><a class="menu-header__item" href="#">Полезные ссылки</a></li>
        </ul>
    </header>
</template>

<script setup>

</script>

<style lang="scss" scoped src="./HeaderProject.scss"/>