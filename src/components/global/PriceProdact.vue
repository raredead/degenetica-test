
<template>
    <div class="prodact-card__price price-card">
        <span class="price-card__new"><slot></slot>₽</span>
        <span class="price-card__old"><slot></slot>₽</span>
    </div>
</template>

<style lang="scss" scoped>
.price-card {
    font-family: 'PT Sans';

    &__new {
        font-size: 16px;
        font-weight: bold;
        padding-right: 8px;
    }

    &__old {
        font-weight: 400;
        font-size: 12px;
        color: var(--color-font-second);
        text-decoration: line-through;
    }
}
</style>