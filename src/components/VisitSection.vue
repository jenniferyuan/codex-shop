<script setup>
const emit = defineEmits(['reserve'])
</script>

<template>
<section class="reserve wrap" id="visit">
<div class="eyebrow" >THERE'S A SEAT FOR YOU</div>
<h2>今晚，來我們這裡吃飯吧。</h2>
<p>午餐 11:30 – 14:30 · 晚餐 17:30 – 21:30<br>不用特別的理由，你來，就是值得好好吃飯的一天。</p>
<button class="button" @click="emit('reserve')">預訂你的餐桌 ↗</button>
</section>
</template>
