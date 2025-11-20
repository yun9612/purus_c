<template>
  <!-- 통계 -->
  <div class="p-4">
    <!-- 통계 카드 -->
    <DashboardStats :stats="stats" />
  </div>
</template>

<script setup>
import DashboardStats from "@/components/admin/DashboardStats.vue";

// 통계 더미
const stats = [
  {
    title: "2025년 예약 내역",
    value: "370",
    unit: "건",
    desc: "취소 건수 23건",
  },
  {
    title: "2025년 누계 수입",
    value: "34,750,000",
    unit: "원",
    desc: "환불 금액 -75,000원",
  },
];
</script>
