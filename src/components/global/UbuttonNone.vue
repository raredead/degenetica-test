<template>
    <div class="btn-none">
        <a href="" class="btn-none__message"><slot></slot></a>
    </div>
</template>

<style lang="scss" scoped>
.btn-none{
    width: 300px;
    display: flex;
    align-items: center;
    justify-content: center;

    margin-top: 30px;
    border: 1px solid var(--color-font-second);
    padding: 12px 16px;
    border-radius: 4px;
    cursor: pointer;
    transition: .3s ease-in;

    &__message {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: bold;
        color: var(--color-font-second);
    }
}

.btn-none:hover {
    background-color: var(--color-font-hover);
}
</style>