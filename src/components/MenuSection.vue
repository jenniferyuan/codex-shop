<script setup>
import { computed, ref } from 'vue'
import { categories, dishes } from '../data/menu'

const selectedCategory = ref('all')
const visibleDishes = computed(() => dishes.filter(dish => selectedCategory.value === 'all' || dish.category === selectedCategory.value))
</script>

<template>
<section class="menu" id="menu">
<div class="section-head">
<div>
<div class="eyebrow">灶間飄香 · 今日好菜</div>
<h2>每一道，都有我們的用心。</h2>
<p>簡單的食材，不簡單的滋味。找到屬於你的那一盤。</p>
</div>
<a href="#menu" class="text-link" id="all-menu" @click="selectedCategory = 'all'">查看完整菜單 ↗</a>
</div>
<div class="tabs" aria-label="餐點分類">
<button v-for="category in categories" :key="category.id" class="tab" :class="{ active: selectedCategory === category.id }" :aria-pressed="selectedCategory === category.id" @click="selectedCategory = category.id">{{ category.label }}</button>
</div>
<div class="dishes" id="dishes" aria-live="polite">
<article v-for="dish in visibleDishes" :key="dish.category" class="dish">
<div class="dish-photo">
<img :src="`https://images.unsplash.com/${dish.image}?auto=format&fit=crop&w=800&q=85`" :alt="dish.name" loading="lazy">
<span class="tag">{{ dish.tag }}</span>
</div>
<div class="dish-title">
<h3>{{ dish.name }}</h3>
<span class="price">NT$ {{ dish.price }}</span>
</div>
<p>{{ dish.description }}</p>
</article>
</div>
</section>
</template>
