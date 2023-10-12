<script setup>

</script>

<template>
    <aside class="aside-price">
        <div class="aside-price__title">Цена</div>
        <div class="aside-price__filter">
            <input 
            type="text" 
            class="aside-price__count"
            placeholder="от 5500 ₽"
            >
            <hr>
            <input 
            type="text" 
            class="aside-price__count"
            placeholder="до 5500 ₽"
            >
        </div>
    </aside>
</template>

<style lang="scss" scoped>
.aside-price {
    padding: 30px 0;

    &__title {
        font-family: 'PT Sans';
        font-weight: bold;
        font-size: 16px;
        padding-bottom: 15px;
        text-align: center;
    }

    &__filter {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    &__count {
        font-family: 'PT Sans';
        font-weight: 400;
        font-size: 14px;
        width: 105px;
        height: 36px;
        border: 1px solid var(--color-border);
        border-radius: 4px;
        outline: none;
        padding-left: 15px;
    }
}

hr{
    width: 10px;
}
</style>