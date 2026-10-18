<script setup>
const emit = defineEmits(['reserve'])
</script>

<template>
<header>
<a class="brand" href="#" aria-label="袁家首頁">袁家<span>小館</span>
</a>
<nav aria-label="主選單">
<a href="#story">關於我們</a>
<a href="#menu">探索菜單</a>
<a href="#visit">來店資訊</a>
<button class="nav-cta" @click="emit('reserve')">預訂餐桌 <span>↗</span>
</button>
</nav>
</header>
</template>
