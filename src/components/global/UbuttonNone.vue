<template>
    <div class="btn-none">
        <a href="" class="btn-none__message">
            <slot></slot>
        </a>
    </div>
</template>

<style lang="scss" scoped>
.btn-none {
    width: 300px;
    display: flex;
    align-items: center;
    justify-content: center;

    margin-top: 35px;
    border: 1px solid var(--color-font-second);
    padding: 12px 16px;
    border-radius: 4px;
    cursor: pointer;
    transition: .3s ease-in;

    @media (max-width: 1650px) {
        padding: 7px 15px;
        width: 130px;
    }

    &__message {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: bold;
        color: var(--color-font-second);

        @media (max-width: 500px) {
            font-size: 12px;
        }
    }
}

.btn-none:hover {
    background-color: var(--color-font-hover);
}
</style>