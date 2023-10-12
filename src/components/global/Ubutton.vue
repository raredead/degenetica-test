
<template>
    <div class="btn-card">
        <a href="" class="btn-card__buy"><slot></slot></a>
    </div>
</template>

<style lang="scss" scoped>
.btn-card{
    width: 75px;
    display: flex;
    align-items: center;
    justify-content: center;

    margin-top: 16px;
    border: 1px solid var(--color-brand);
    padding: 12px 16px;
    border-radius: 4px;
    cursor: pointer;
    transition: .3s ease-in;

    &__buy {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: bold;
        color: var(--color-brand);
    }
}

.btn-card:hover {
    background-color: var(--color-font-hover);
}
</style>