<template>
  <div class="flex gap-3 mb-6">
    <div
      v-for="(card, index) in stats"
      :key="index"
      class="first px-10 bg-white dark:bg-gray-800 rounded-2xl shadow-sm h-[180px] content-around py-4 hover:shadow-lg transition-shadow">
      <div class="flex items-center flex-col text-center gap-3">
        <div class="flex flex-col gap-1">
          <p class="text-gray-500 text-lg font-bold">{{ card.title }}</p>
          <p v-if="card.date" class="text-gray-500 text-xs">{{ card.date }}</p>
          <p class="text-[#555555]">
            <span
              class="text-2xl font-bold text-[#296af1]"
              :class="[
                card.link ? 'text-2xl' : 'text-6xl leading-17',
                card.value === '21' ? 'text-red-500' : '',
                card.value === '3' ? 'text-red-500' : '',
              ]">
              {{ card.value }}
            </span>
            {{ card.unit }}
          </p>
          <p
            v-if="card.desc"
            :class="card.desc === '환불 금액 -75,000원' ? 'text-red-500' : ''"
            class="text-sm mt-1 text-[#555555]">
            {{ card.desc }}
          </p>
          <button
            class="bg-[#296af1] mt-1 w-20 sm:w-[120px] text-white py-2 text-xs rounded-lg"
            v-if="card.link">
            {{ card.link }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  stats: {
    type: Array, // 배열타입
    required: true, // 필수 속성
    default: () => [], // 기본 값을 배열로 초기화
  },
});
</script>

<style scoped lang="scss">
.first:first-child {
  background-color: #296af1;
  div {
    div {
      p {
        color: #ffffff;
      }
      span {
        color: #f0faff;
      }
    }
  }
}
</style>
