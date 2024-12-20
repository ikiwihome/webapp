<template>
  <main class="home">
    <LinkCard v-for="card in cards" :key="card.id" :icon="card.icon" :title="card.title" :link="card.link"
      :tooltip="card.tooltip" />
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

// 动态导入图片
import ikiwi from '@/assets/images/ikiwi.png'
import personal from '@/assets/images/10021.png'
import aiChat from '@/assets/images/ai-chat.png'
import note from '@/assets/images/note.png'
import cloudDisk from '@/assets/images/cloud-disk.png'

const cards = ref([
  {
    id: 1,
    icon: ikiwi,
    title: 'ikiwi温暖小窝',
    link: '#',
    tooltip: '这是 ikiwi 温暖小窝的描述',
  },
  {
    id: 2,
    icon: personal,
    title: '个人主页',
    link: '#',
    tooltip: '这是个人主页的描述',
  },
  {
    id: 3,
    icon: aiChat,
    title: 'AI聚合聊天',
    link: '#',
    tooltip: '这是 AI 聚合聊天的描述',
  },
  {
    id: 4,
    icon: note,
    title: '为知笔记',
    link: '#',
    tooltip: '这是为知笔记的描述',
  },
  {
    id: 5,
    icon: cloudDisk,
    title: '手机云盘',
    link: '#',
    tooltip: '这是手机云盘的描述',
  },
])
</script>

<style scoped>
.home {
  position: fixed;
  bottom: 40px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 auto;
}
</style>
