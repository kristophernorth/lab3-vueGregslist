<script setup>
import { House } from '@/models/House';

defineProps({
  houseProp: { type: House, required: true}
})
</script>


<template>
  <div class="row">
    <div class="row bg-light shadow" :style="{ borderColor: houseProp.bedrooms }">
    <div class="col-md-4 px-0">
      <img :src="houseProp.imgUrl" :alt="`${houseProp.bedrooms} ${houseProp.bathrooms}`" class="img-fluid house-img">
    </div>
    <div class="col-md-8">
      <div class="p-2 d-flex flex-column justify-content-between h-100">
        <div>
          <h2>{{ houseProp.year }} {{ houseProp.bedrooms }} {{ houseProp.bathrooms }}</h2>
          <p class="fs-3">${{ houseProp.price }}</p>
          <p>{{ houseProp.description }}</p>
        </div>
        <div class="text-end">
          <span>{{ houseProp.creator.name }}</span>
          <img :src="houseProp.creator.picture" :alt="houseProp.creator.name" class="creator-img ms-3">
        </div>
      </div>
    </div>
  </div>
  </div>
</template>


<style lang="scss" scoped>
.house-img {
  height: 45dvh;
  width: 100%;
  object-fit: cover;
}

.row {
  border: 3px solid;
}

.creator-img {
  height: 10dvh;
  aspect-ratio: 1/1;
  border-radius: 50%;
  object-fit: cover;
}
</style>