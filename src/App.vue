<script setup>
import { ref } from "vue";

const showForm = ref(false);
</script>
<template>
  <main>
    <div class="container">
      <header>
        <h1>Memo</h1>
        <button @click="showForm = true">+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </p>
          <p class="date">
            {{ new Date().toLocaleDateString("en-us") }}
          </p>
        </div>
        <div class="card">
          <p class="main-text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </p>
          <p class="date">
            {{ new Date().toLocaleDateString("en-us") }}
          </p>
        </div>
      </div>
    </div>
    <div v-if="showForm" class="overlay">
      <div class="modal">
        <button @click="showForm = false" class="close-btn">&times;</button>
        <textarea name="note" id="note" cols="30" rows="10"></textarea>
        <button class="save-btn">Save</button>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  width: 100vw;
}
.container {
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h1 {
  font-weight: bold;
  margin-bottom: 25px;
  font-size: 50px;
  color: #495a7d;
}
header button {
  border: none;
  padding: 10px;
  width: 40px;
  height: 40px;
  cursor: pointer;
  background-color: #495a7d;
  border-radius: 100%;
  color: white;
}
.cards-container {
  display: flex;
  flex-wrap: wrap;
}
.card {
  width: 225px;
  height: 225px;
  background-color: #ffa6c1;
  padding: 12px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}
.date {
  font-size: 12.5px;
  font-weight: bold;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.77);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  width: 420px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;
}

.save-btn {
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: #495a7d;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  margin-top: 15px;
  color: white;
}
/* create close button style */
.close-btn {
  position: absolute;
  top: 5px;
  right: 10px;
  width: 30px;
  height: 30px;
  background-color: transparent;
  border: none;
  font-size: 25px;
  cursor: pointer;
}
</style>
