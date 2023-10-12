
<template>
    <div class="img-card__discount discount">
        <span class="discount__size"><slot></slot>%</span>
    </div>
</template>

<style lang="scss" scoped>
.discount {
    position: absolute;
    left: 12px;
    bottom: 12px;
    padding: 6px 10px;
    background-color: var(--color-brand);
    border-radius: 4px;

    &__size {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: bold;
        color: var(--color-white);
    }
}
</style>