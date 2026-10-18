<script setup>
import { computed, reactive, ref } from 'vue'

const dialog = ref(null)
const submitted = ref(false)
const minimumDate = ref('')
const form = reactive({ name: '', date: '', guests: '2 位', time: '11:30' })
const times = ['11:30', '12:30', '13:30', '17:30', '18:30', '19:30', '20:30']
const confirmation = computed(() => `${form.name}，你的訂位預覽：${form.date} ${form.time}，${form.guests}。此為示範預覽，尚未建立實際訂位。`)

function open() {
  const today = new Date()
  minimumDate.value = `${today.getFullYear()}-${String(today.getMonth() + 1).padStart(2, '0')}-${String(today.getDate()).padStart(2, '0')}`
  submitted.value = false
  if (!dialog.value.open) dialog.value.showModal()
}
function close() { dialog.value.close() }
function closeOnBackdrop(event) {
  if (event.target !== dialog.value) return
  const rect = dialog.value.getBoundingClientRect()
  if (event.clientX < rect.left || event.clientX > rect.right || event.clientY < rect.top || event.clientY > rect.bottom) close()
}
function submit() { submitted.value = true }
defineExpose({ open })
</script>

<template>
  <dialog id="booking" ref="dialog" aria-labelledby="booking-title" aria-describedby="booking-description" @click="closeOnBackdrop">
    <button class="close" aria-label="關閉" @click="close">×</button>
    <h2 id="booking-title">為相聚，留一張餐桌。</h2>
    <p id="booking-description">此為訂位體驗示範，資料僅保留在目前頁面，不會送出實際訂位。</p>
    <form v-show="!submitted" id="booking-form" @submit.prevent="submit">
      <label>稱呼<input v-model="form.name" name="name" required placeholder="怎麼稱呼你？" maxlength="50">
</label>
      <div class="form-grid">
        <label>用餐日期<input v-model="form.date" name="date" type="date" :min="minimumDate" required>
</label>
        <label>用餐人數<select v-model="form.guests" name="guests">
<option v-for="count in [2, 1, 3, 4, 5, 6]" :key="count">{{ count }} 位</option>
</select>
</label>
      </div>
      <label>用餐時間<select v-model="form.time" name="time">
<option v-for="time in times" :key="time">{{ time }}</option>
</select>
</label>
      <button class="button booking-submit" type="submit">預覽訂位資訊 ↗</button>
    </form>
    <div v-if="submitted" id="confirmation" role="status">{{ confirmation }}</div>
  </dialog>
</template>
