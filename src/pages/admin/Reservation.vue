<template>
  <!-- 금일 예약 관리 -->
  <div class="p-4">
    <!-- 통계 카드 -->
    <DashboardStats :stats="stats" />
  </div>
</template>

<script setup>
import DashboardStats from "@/components/admin/DashboardStats.vue";

const today = new Date().toLocaleDateString("ko-KR", {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric",
});
// 예약 더미
const stats = [
  {
    title: today,
    value: "64",
    unit: "건",
  },
  {
    title: "진행 중 작업",
    value: "80",
    unit: "%",
  },
  {
    title: "금일 결제액",
    value: "21",
    unit: "건",
  },
  {
    title: "리뷰 현황",
    value: "0",
    unit: "건",
  },
  {
    title: "리뷰 현황",
    value: "30",
    unit: "건",
  },
];
</script>
