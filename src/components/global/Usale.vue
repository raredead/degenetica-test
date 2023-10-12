<template>
    <div class="img-card__hot hot-card">
        <span class="hot-card__txt">Хит продаж</span>
        <img src="../../img/prodact-card/fire.svg" alt="">
    </div>
</template>

<style lang="scss" scoped>
.hot-card {
    position: absolute;
    top: 12px;
    left: 12px;

    background-color: var(--color-white);
    display: flex;
    align-items: center;
    padding: 8px;

    &__txt {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: 400;
        padding-right: 5px;
    }
}
</style>