<script setup>
import { ref } from 'vue';

const sizeNum = ref([
    { id: 1, title: 'Атрибут' },
    { id: 2, title: 'Атрибут' },
    { id: 3, title: 'Атрибут' },
    { id: 4, title: 'Атрибут' },
    { id: 5, title: 'Атрибут' },
    { id: 6, title: 'Атрибут' },
])

const titleSize = 'Размер'


</script>

<template>
<aside class="aside-size">
    <div class="aside-size__title">{{ titleSize }}</div>
        <div class="aside-size__atributs atributs-size">
            <div class="atributs-size__item" v-for="item in sizeNum" :key="item.id">
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
.aside-size {

    &__title {
        font-family: 'PT Sans';
        font-weight: bold;
        font-size: 16px;
        text-align: center;
        padding: 28px 0 16px;
    }
}

.atributs-size{
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