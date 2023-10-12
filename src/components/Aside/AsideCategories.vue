<script setup>
const categoryName = 'Название категории'
const countCategories = 3
</script>

<template>
    <aside class="aside-categories">
        <nav class="aside-categories__title">
            <ul class="aside-categories__main">
                <a href="#" class="aside-categories__item">
                    <span>{{ categoryName }}</span>
                    <span class="aside-categories__count">{{ countCategories }}</span>
                </a>
                <ul class="aside-categories__sub">
                    <a href="#" class="aside-categories__item">
                        <span>{{ categoryName }}</span>
                        <span class="aside-categories__count">{{ countCategories }}</span>
                    </a>
                    <a href="#" class="aside-categories__item">
                        <span>{{ categoryName }}</span>
                        <span class="aside-categories__count">{{ countCategories }}</span>
                    </a>
                    <a href="#" class="aside-categories__item">
                        <span>{{ categoryName }}</span>
                        <span class="aside-categories__count">{{ countCategories }}</span>
                    </a>
                </ul>
            </ul>
        </nav>
    </aside>
</template>

<style lang="scss" scoped>
.aside-categories {
    &__title {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: 400;
        color: var(--color-font-main);
    }

    &__sub{
        padding-left: 30px;
    }

    &__item {
        display: flex;
        justify-content: space-between;
        margin-bottom: 5px;
        color: var(--color-font-main);
        padding: 5px;
        transition: .3s ease-in;
    }
    
    &__item:hover {
        background-color: var(--color-font-bg);
    }

    &__count {
        color: var(--color-font-second);
    }
}
</style>