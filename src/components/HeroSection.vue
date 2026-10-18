<script setup>
const emit = defineEmits(['reserve'])
</script>

<template>
<section class="hero">
<div>
<div class="eyebrow">一桌家常 · 一席團圓</div>
<h1>飯做好了，<br>就等<span class="italic">你來</span>
</h1>
<p>熱菜上桌，白飯盛好，熟悉的香氣正暖。<br>招呼在意的人，一起吃飯，把日子慢慢聊。</p>
<div class="hero-actions">
<a class="button" href="#menu">探索我們的菜單 <span>↗</span>
</a>
<button class="text-link hero-booking" @click="emit('reserve')">預訂美好時光 ↗</button>
</div>
<div class="hero-bottom">
<span class="hero-symbol">❧</span>
<div>
<div class="stars">時令鮮味 · 手作家常 · 暖心上桌</div>以當季食材，款待每一個平凡的日子</div>
</div>
</div>
<div class="hero-visual">
<img class="hero-image" src="https://images.unsplash.com/photo-1563245372-f21724e3856d?auto=format&fit=crop&w=1200&q=85" alt="竹蒸籠盛裝的中式點心">
<div class="seal">用心做菜<b>家</b>好好吃飯</div>
<div class="photo-caption">一桌好菜，滿席溫暖。<small>把今晚，留給相聚。</small>
</div>
</div>
</section>
<div class="values">
<span>
<i>❧</i> 嚴選當季・新鮮直送</span>
<span>
<i>♧</i> 每日手作・真實滋味</span>
<span>
<i>♜</i> 家常滋味・在地風土</span>
<span>
<i>♡</i> 為相聚而準備的餐桌</span>
</div>
</template>

<style scoped>
.hero-actions .button {
  background: #2563eb;
  border-color: #2563eb;
  color: #fff;
}

.hero-actions .button:hover {
  background: #1d4ed8;
  border-color: #1d4ed8;
}
</style>
