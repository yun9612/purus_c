<template>
  <div>
    <!-- 타이틀 -->
    <h1 class="text-xl font-bold text-[#092857]">고객 목록</h1>
    <div v-for="customer in dataCustomer" :key="customer.id" class="mt-4 flex flex-col mb-3">
      <div class="flex items-center gap-5 bg-[#f0faff] px-3 py-4 rounded-2xl">
        <!-- 썸네일 -->
        <span class="bg-[#dce7fb] px-4 py-3 rounded-full text-2xl font-bold text-[#092857]">
          {{ customer.cafename[0] }}
        </span>
        <div class="flex flex-col gap-1">
          <div class="flex items-center gap-2">
            <i class="fa-solid fa-user text-sm text-[#888888]"></i>
            <p class="text-[14px]">{{ customer.name }}({{ customer.cafename }})</p>
          </div>
          <div class="flex items-center gap-2">
            <i class="fa-solid fa-phone text-sm text-[#888888]"></i>
            <p class="text-[14px]">{{ customer.phone }}</p>
          </div>
        </div>
        <div class="flex flex-col gap-1">
          <div class="flex items-center gap-2">
            <i class="fa-solid fa-location-dot text-sm text-[#888888]"></i>
            <p class="text-[14px]">{{ customer.addr }}</p>
          </div>
          <div class="flex items-center gap-2">
            <i class="fa-solid fa-calendar-check text-sm text-[#888888]"></i>
            <p class="text-[14px]">{{ customer.date }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import customerData from "@/data/customer.json";
import { ref } from "vue";
// 더미데이터 불러오기
const dataCustomer = ref(customerData);
</script>
