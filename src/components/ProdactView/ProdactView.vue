<script setup>
import Ubutton from '../global/Ubutton.vue';
import Usale from '../global/Usale.vue';
import Udiscount from '../global/Udiscount.vue';
import PriceProdact from '../global/PriceProdact.vue';
import UbuttonNone from '../global/UbuttonNone.vue'

import { ref } from 'vue';

const projectInfo = ref([
    { id: 1, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 2, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 3, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 0 },
    { id: 4, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 5, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 6, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 7, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 8, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 9, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 10, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 11, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
    { id: 12, brand: 'Бренд', description: 'Полное название товара в несколько строк для вида с обрывом в конце...', price: 5590 },
])
</script>

<template>
    <div class="view-prodact">
        <div 
        class="prodact-card" 
        v-for="item in projectInfo"
        :key="item.id"
        >
            <div class="prodact-card__img img-card">
                <img src="../../img/prodact-card/img-prodact.png" alt="" class="img-card__main">
                <Usale />
                <Udiscount>
                    25
                </Udiscount>
            </div>
            <div class="prodact-card__brand">{{ item.brand }}</div>
            <div class="prodact-card__txt">{{ item.description }}</div>
            <div v-if="item.price !== 0">
                <PriceProdact>{{ item.price }}</PriceProdact>
                <Ubutton>
                    Купить
                </Ubutton>
            </div>
            <div v-else>
                <UbuttonNone>
                    Сообщить о поступлении
                </UbuttonNone>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped src="./ProdactView.scss"/>