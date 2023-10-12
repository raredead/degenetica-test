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

    if(a.length === 0) {
        return [
            {
                id: 0,
                title: 'По вашему запросу ничего не найдено',
            },
        ]
    }

    return a;
})

// Кнопка удаления
document.addEventListener('DOMContentLoaded', () => {
    const searchInput = document.querySelector('.aside-brand__search');
    const searchRemoveButton = document.querySelector('.search-brand__remove');

    searchInput.addEventListener('input', () => {
        if (searchInput.value.length > 0) {
            searchRemoveButton.classList.add('--active');
        } else {
            searchRemoveButton.classList.remove('--active');
        }
    });

    searchRemoveButton.addEventListener('click', () => {
        searchInput.value = '';
        searchRemoveButton.classList.remove('--active');
        searchRemoveButton.classList.add('--hidden');
    });
});
</script>

<template>
    <aside class="aside-brand">
        <div class="aside-brand__header header-aside">
            <div class="header-aside__title">{{ titleBrand }}</div>
            <button class="header-aside__btn">Очистить</button>
        </div>
        <div class="wrap">
            <input 
                type="text" 
                class="aside-brand__search"
                placeholder="Поиск"
                v-model="query"
            >
            <button class="search-brand__remove">
                <svg class="remove" width="18" height="18" viewBox="0 0 18 18" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                        d="M17.3334 9.00001C17.3334 13.6024 13.6025 17.3333 9.00008 17.3333C4.39771 17.3333 0.666748 13.6024 0.666748 9.00001C0.666748 4.39764 4.39771 0.666679 9.00008 0.666679C13.6025 0.666679 17.3334 4.39764 17.3334 9.00001ZM12.0893 7.08927C12.4148 6.76383 12.4148 6.23619 12.0893 5.91076C11.7639 5.58532 11.2363 5.58532 10.9108 5.91076L9.00008 7.8215L7.08934 5.91076C6.7639 5.58532 6.23626 5.58532 5.91083 5.91076C5.58539 6.23619 5.58539 6.76383 5.91083 7.08927L7.82157 9.00001L5.91083 10.9108C5.58539 11.2362 5.58539 11.7638 5.91083 12.0893C6.23626 12.4147 6.7639 12.4147 7.08934 12.0893L9.00008 10.1785L10.9108 12.0893C11.2363 12.4147 11.7639 12.4147 12.0893 12.0893C12.4148 11.7638 12.4148 11.2362 12.0893 10.9108L10.1786 9.00001L12.0893 7.08927Z" />
                </svg>
            </button>
        </div>
        <div class="aside-brand__atributs atributs-brand" v-if="queryAtributs !== 0">
            <div class="atributs-brand__item" v-for="item in queryAtributs" :key="item.id">
                <label>
                    <input 
                    type="checkbox" 
                    class="check"
                    v-if="item.title !== 'По вашему запросу ничего не найдено'"
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
        border-radius: 4px;

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

.wrap{
    position: relative;
}
.search-brand{
&__remove {
        position: absolute;
        top: 25px;
        right: 5px;
        background-color: transparent;
        border: none;
        cursor: pointer;
        display: none;
    }

    &__remove.--active {
        display: block;
    }
}
.remove {
    fill: var(--color-icons);
}
</style>