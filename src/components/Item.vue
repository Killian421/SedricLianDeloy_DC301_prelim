<!-- eslint-disable vue/multi-word-component-names -->
<!-- src/components/Item.vue -->
<template>
  <div v-if="isVisible" class="item">
    <h2 class="item-name">{{ item.name }}</h2>
    <p class="item-price">Price: ${{ item.price.toFixed(2) }}</p>
    <button class="add-to-cart-button" @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  computed: {
    isVisible() {
      return this.item.visible
    }
  },
  methods: {
    addToCart() {
      console.log('Item added: ${this.item.name}, Price: ${this.item.price}')
      this.$emit('add-to-cart', this.item)
    }
  }
}
</script>

<style scoped>
.item {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 16px;
  margin: 12px 0;
  background-color: #7b7777;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.item:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
}

.item-name {
  font-size: 1.5em;
  margin: 0;
  color: #333;
}

.item-price {
  font-size: 1.2em;
  color: #fff;
  margin: 8px 0;
}

.add-to-cart-button {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1em;
  transition: background-color 0.3s ease;
}

.add-to-cart-button:hover {
  background-color: #0056b3;
}
</style>
