<template>
  <div id="app" class="app-container">
    <ItemList />
  </div>
</template>

<script>
import ItemList from './components/Itemlist.vue'

export default {
  components: {
    ItemList
  }
}
</script>

<style>
#app {
  text-align: center;
  background-color: #e9ecef;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.app-container {
  width: 100%;
  max-width: 900px;
  padding: 20px;
  background-color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}
</style>
