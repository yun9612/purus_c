<template>
  <!-- 고객 리뷰 관리 -->
  <div class="p-4">
    <!-- 통계 카드 -->
    <DashboardStats :stats="stats" />
  </div>
</template>

<script setup>
import DashboardStats from "@/components/admin/DashboardStats.vue";

// 고객 리뷰 더미
const stats = [
  {
    title: "총점 현황",
    value: "4.9",
    unit: "점",
  },
  {
    title: "총 리뷰수",
    value: "233",
    unit: "건",
  },
  {
    title: "리뷰 작성률",
    value: "63",
    unit: "%",
  },
  {
    title: "쿠폰 지급 예정",
    value: "1",
    unit: "건",
  },
  {
    title: "재방문 신청",
    value: "3",
    unit: "건",
  },
];
</script>
