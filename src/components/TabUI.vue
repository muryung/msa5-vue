<script setup>
  import { ref } from 'vue';

  let currBtn = ref(null);

  const toggleBtn = (e) => {
    currBtn.value?.classList.remove('active');
    currBtn.value = e.target;
    currBtn.value.classList.add('active');
  };
</script>

<template>
  <div class="container">
    <div class="buttons">
      <div @click="toggleBtn" class="profile" :class="active">프로필</div>
      <div @click="toggleBtn" class="setting" :class="active">설정</div>
      <div @click="toggleBtn" class="dashboard" :class="active">게시판</div>
    </div>

    <p v-if="currBtn?.classList.contains('profile')">프로필 페이지 입니다.</p>
    <p v-else-if="currBtn?.classList.contains('setting')">설정 페이지 입니다.</p>
    <p v-else-if="currBtn?.classList.contains('dashboard')">게시판 페이지 입니다.</p>
  </div>
</template>

<style>
  .container {
    width: 500px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .buttons {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  .buttons div {
    border: 1px solid rgba(0, 0, 0, 0.144);
    border-radius: 5px;
    padding: 10px;
  }

  .active {
    background-color: rgb(186, 255, 249);
  }
</style>