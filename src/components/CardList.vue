<script setup>
// 	- baseURL: https://picsum.photos/v2/list
// 	- paramers:
// 	  - page: number
// 	  - limit: number

import axios from 'axios';
import { onBeforeMount, ref } from 'vue';

const cards = ref([]);
const page = ref(1);
const limit = 3;
const idx = ref(0);
const cardContainer = ref(null);

const getNextPage = async () => {
  try {
    const url = 'https://picsum.photos/v2/list';

    const config = {
      params: {
        page: page.value,
        limit
      }
    };

    if (cards.value.length != 0) {
      for (let i = idx.value; i < idx.value + 3; ++i) {
        cardContainer.value.childNodes[i].style.display = 'flex';
      }

      idx.value += 3;
    }
    
    const response = await axios.get(url, config);
    cards.value.push(...response.data);

    page.value++;
  } catch (error) {
    console.error(error);
  }
};

const reset = () => {
  // cards.value = [];
  // page.value = 1;

  cards.value = cards.value.slice(0, limit);
  page.value = 2;
}

onBeforeMount(getNextPage);
</script>

<template>
  <div ref="cardContainer" class="card-container">
    <div v-for="item in cards" :key="item.id" class="card">
      <div class="card-img" :style="{backgroundImage: `url(${item.download_url})`}"></div>
      <div class="card-text">{{ item.id }}: {{ item.author }}</div>
    </div>
  </div>
  <div>
    <button @click="getNextPage">다음 페이지</button>
    <button @click="reset">리셋</button>
  </div>
</template>

<style scoped>
.card-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 10px;
}

.card {
  display: none;
  flex-direction: column;
  gap: 10px;
}

.card-img {
  aspect-ratio: 4/3;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}


</style>