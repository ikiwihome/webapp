<template>
  <div class="card-outer">
    <div class="tooltip">{{ tooltip }}</div>
    <div class="card-wrapper">
      <div class="card-container">
        <a :href="link" class="card">
          <div class="icon">
            <img :src="icon" :alt="title" />
          </div>
          <span class="text">{{ title }}</span>
          <div class="arrow">
            <svg class="svg-inline--fa fa-arrow-alt-to-right fa-w-14" aria-hidden="true" data-prefix="fas"
              data-icon="arrow-alt-to-right" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
              <path fill="currentColor"
                d="M448 88v336c0 13.3-10.7 24-24 24h-24c-13.3 0-24-10.7-24-24V88c0-13.3 10.7-24 24-24h24c13.3 0 24 10.7 24 24zM24 320h136v87.7c0 17.8 21.5 26.7 34.1 14.1l152.2-152.2c7.5-7.5 7.5-19.8 0-27.3L194.1 90.1c-12.6-12.6-34.1-3.7-34.1 14.1V192H24c-13.3 0-24 10.7-24 24v80c0 13.3 10.7 24 24 24z" />
            </svg>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  icon: string
  title: string
  link: string
  tooltip: string
}>()
</script>

<style scoped>
.card-outer {
  position: relative;
  margin: 20px;
}

.card-wrapper {
  width: 270px;
  position: relative;
  overflow: visible;
}

.card-container {
  width: 100%;
  overflow: hidden;
  border-radius: 8px;
  position: relative;
}

.card {
  background: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(10px);
  border-radius: 8px;
  height: 90px;
  display: flex;
  align-items: center;
  position: relative;
  cursor: pointer;
  padding: 0 16px;
  color: white;
  transition: background-color 0.3s;
  text-decoration: none;
}

.card::after {
  background: hsla(0, 0%, 100%, 0.1);
  border-radius: 50%;
  box-shadow: 0 0 40px 0 rgba(0, 0, 0, 0.2);
  content: '';
  height: 90px;
  position: absolute;
  right: -48px;
  top: 0;
  width: 90px;
  transition: background 0.3s;
}

.icon {
  align-items: center;
  display: flex;
  flex: 0 0 60px;
  height: 60px;
  justify-content: center;
  margin-right: 15px;
  width: 60px;
  z-index: 1;
}

.icon img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.text {
  flex: 1;
  font-size: 16px;
  z-index: 1;
}

.arrow {
  height: 100%;
  line-height: 90px;
  padding-right: 10px;
  position: absolute;
  right: 0px;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1;
  opacity: 0.6;
  display: flex;
  align-items: center;
  pointer-events: none;
  width: auto;
}

.arrow svg {
  width: 24px;
  height: 24px;
  margin-right: 0;
}

.tooltip {
  -webkit-backdrop-filter: blur(8px);
  backdrop-filter: blur(8px);
  background: rgba(0, 0, 0, 0.784);
  border-radius: 5px;
  bottom: 110px;
  color: #fff;
  font-size: 13px;
  left: 0;
  opacity: 0;
  padding: 25px;
  pointer-events: none;
  position: absolute;
  right: 0;
  transform: translateY(-20px);
  transition: all 0.3s;
  z-index: 0;
}

/* 修改悬停选择器 */
.card-outer:hover .tooltip {
  opacity: 1;
  transform: translateY(0);
  z-index: 4;
}

/* 添加悬停时的颜色变化 */
.card-outer:hover .card::after {
  background: hsla(0, 0%, 100%, 0.2);
}
</style>
