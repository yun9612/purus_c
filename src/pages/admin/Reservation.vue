<template>
  <!-- 금일 예약 관리 -->
  <div class="p-4">
    <!-- 통계 카드 -->
    <DashboardStats :stats="stats" />

    <div class="overflow-x-auto">
      <table class="min-w-full text-center">
        <thead>
          <tr class="border-b border-t border-gray-300 bg-gray-100">
            <th class="py-3 px-3 font-medium opacity-70">예약 일자</th>
            <th class="py-3 px-3 font-medium opacity-70">예약자명</th>
            <th class="py-3 px-3 font-medium opacity-70">연락처</th>
            <th class="py-3 px-3 font-medium opacity-70">주소</th>
            <th class="py-3 px-3 font-medium opacity-70">담당 기사</th>
            <th class="py-3 px-3 font-medium opacity-70">제빙기 모델</th>
            <th class="py-3 px-3 font-medium opacity-70">결제 금액</th>
            <th class="py-3 px-3 font-medium opacity-70">신청일</th>
            <th class="py-3 px-3 font-medium opacity-70">관리</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in filteredData" :key="item.id" class="border-b border-gray-200">
            <td class="py-3 px-3 opacity-80">{{ item.date }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.name }}({{ item.cafename }})</td>
            <td class="py-3 px-3 opacity-80">{{ item.phone }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.address }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.driver }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.model }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.price }}</td>
            <td class="py-3 px-3 opacity-80">{{ item.reserDate }}</td>
            <td class="py-3 px-3 opacity-80">
              <select v-model="item.status" class="border rounded px-2 py-1 text-sm">
                <option value="waiting">진행 예정</option>
                <option value="cancel">취소</option>
                <option value="done">완료</option>
              </select>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- 페이지네이션 -->
    <div class="flex justify-center mt-4 space-x-2">
      <button
        v-for="page in totalPages"
        :key="page"
        @click="currentPage = page"
        :class="{
          'bg-blue-500 text-white': currentPage === page,
          'bg-gray-200 text-gray-700': currentPage !== page,
        }"
        class="px-3 py-1 rounded">
        {{ page }}
      </button>
    </div>
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
