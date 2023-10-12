<script setup>
import HeaderProcect from './components/header/HeaderProcect.vue';
import AsideCategoties from './components/Aside/AsideCategories.vue';
import AsidePrice from './components/Aside/AsidePrice.vue';
import AsideBrand from './components/Aside/AsideBrand.vue';
import AsideSize from './components/Aside/AsideSize.vue';
import ProdactView from './components/ProdactView/ProdactView.vue';
</script>

<template>
  <div class="container">
    <HeaderProcect />
    <main>
      <div class="assides__block">
        <AsideCategoties />
        <AsidePrice />
        <AsideBrand />
        <AsideSize />
      </div>
      <div class="content__block">
        <ProdactView />
      </div>
    </main>
  </div>
</template>