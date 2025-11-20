<template>
  <!-- 통합 모니터링 -->
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
// 통계카드 더미
const stats = [
  {
    title: "오늘 신규 예약",
    date: today,
    value: "8",
    unit: "건",
    desc: "",
    link: "",
  },
  {
    title: "진행 중 작업",
    value: "64",
    unit: "건",
    desc: "처리 완료 12건",
    link: "예약 관리",
  },
  {
    title: "금일 결제액",
    value: "156,000",
    unit: "원",
    desc: "결제 취소 1건 24,000원",
    link: "매출결산",
  },
  {
    title: "리뷰 현황",
    value: "4.8",
    unit: "점",
    desc: "리뷰 작성률 63%",
    link: "고객 리뷰 관리",
  },
];
</script>
