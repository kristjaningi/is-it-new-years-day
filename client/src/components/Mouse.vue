<template>
  <span
    class="mouse"
    :class="{
      smoothTransition: isSmooth,
    }"
    :style="{
      transform: `translate(-50%, -50%)
        translateX(${isMine ? `${location.x}px` : `${location.x * 100}vw`})
        translateY(${isMine ? `${location.y}px` : `${location.y * 100}vh`}) scale(0.5)`,
    }"
  >
    <img v-if="isMine" src="https://twemoji.maxcdn.com/v/latest/72x72/1f49a.png" />
    <img v-if="!isMine" src="https://twemoji.maxcdn.com/v/latest/72x72/2764.png" />
  </span>
</template>

<script>
export default {
  props: ['location', 'isSmooth', 'isMine'],
};
</script>

<style scoped>
.mouse {
  position: absolute;
  top: 0;
  left: 0;
}

.smoothTransition {
  transition: transform 100ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
</style>
