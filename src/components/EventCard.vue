<template>
      <RouterLink class="text-gray-700 no-underline" :to="{ name: 'event-detail', params: { id: event?.id } }">
        <div class="mb-4">
            <div class="p-5 w-64 cursor-pointer border border-gray-800 transform transition-transform duration-200 hover:scale-101 hover:shadow-md">
        <span>@{{ event?.time }} on {{ event?.date }}</span>
        <h4>{{ event?.title }}</h4>
      </div>
    </div>
  </RouterLink>
  </template>
  
  <script setup lang="ts">
  import type { EventItem } from '@/type'
  import type { PropType } from 'vue';
  const props = defineProps({
    event: {
        type: Object as PropType<EventItem>,
            require: true
    }
})

  </script>
  
  <style scoped>
  .event-card {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
  }
  
  .event-card:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
  }

  .event-link {
    color: #2c3e50;
    text-decoration: none;
  }
  </style>