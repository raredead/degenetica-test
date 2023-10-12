<script setup>
import { ref, computed } from 'vue';

const titleBrand = 'Бренд'

const atributs = ref([
    { id: 1, title: 'Атрибут' },
    { id: 2, title: 'Атрибут' },
    { id: 3, title: 'Атрибут' },
    { id: 4, title: 'Атрибут' },
    { id: 5, title: 'Атрибут' },
    { id: 6, title: 'Атрибут' },
    { id: 7, title: 'Атрибут' },
    { id: 8, title: 'Атрибут' },
    { id: 9, title: 'Атрибут' },
    { id: 10, title: 'Атрибут' },
])

// Фильрация по брендам
const query = ref('')

const queryAtributs = computed(() => {
    let a = atributs.value;
    let seacrh = query.value;

    if(seacrh) {
        a = a.filter((atribut) => atribut.title.indexOf(seacrh) !== -1)
    }

    return a;
})
</script>

<template>
    <aside class="aside-brand">
        <div class="aside-brand__header header-aside">
            <div class="header-aside__title">{{ titleBrand }}</div>
            <button class="header-aside__btn">Очистить</button>
        </div>
        <input 
        type="text" 
        class="aside-brand__search"
        placeholder="Поиск"
        v-model="query"
        >
        <div class="aside-brand__atributs atributs-brand">
            <div class="atributs-brand__item" v-for="item in queryAtributs" :key="item.id">
                <label>
                    <input 
                    type="checkbox" 
                    class="check"
                    >
                    {{ item.title }}
                </label> 
            </div>
        </div>
    </aside>
</template>

<style lang="scss" scoped>

.aside-brand{

    &__search {
        width: 250px;
        height: 36px;
        background: url(../../img/aside-brand/search-brand.svg) left no-repeat;
        background-position: 3px 50%;
        outline: none;
        border: 1px solid var(--color-border);

        font-family: 'PT Sans';
        font-weight: 400;
        font-size: 16px;
        padding-left: 30px;
        margin: 16px 0;
    }

    &__atributs {
        height: 180px;
        overflow-y: auto;
    }

    &__atributs::-webkit-scrollbar {
        width: 3px;
        background-color: var(--color-white);
    }

    &__atributs::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background-color: var(--color-icons);
}

    &__atributs::-webkit-scrollbar-track {
        -webkit-box-shadow: inset 0 0 6px var(--color-white);
        border-radius: 10px;
        background-color: var(--color-white);
}
}
.header-aside {
    display: flex;
    justify-content: space-between;

    &__title {
        font-family: 'PT Sans';
        font-weight: bold;
        font-size: 16px;
    }

    &__btn {
        background-color: transparent;
        border: none;
        text-decoration: underline;
        color: var(--color-font-second);
        cursor: pointer;
        transition: .3s ease-in;
    }

    &__btn:hover {
        color: var( --color-font-hover);
    }
}

.atributs-brand{
    &__item {
        font-family: 'PT Sans';
        font-size: 14px;
        font-weight: 400;
        line-height: 1.2;
        padding-bottom: 12px;
    }
}

.check {
    margin-right: 12px;
}
</style>