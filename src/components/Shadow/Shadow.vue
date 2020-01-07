<template>
  <svg width="214" height="12" viewBox="0 0 214 12" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path
      id="shadow"
      d="M106.715 12C156.816 12 197.43 9.31371 197.43 6C197.43 2.68629 156.816 0 106.715 0C56.6145 0 16 2.68629 16 6C16 9.31371 56.6145 12 106.715 12Z"
      fill="black"
      fill-opacity="0.15"
    />
  </svg>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>

#shadow {
  transform-origin: 50% 50%;
  transform-box: fill-box;
  animation: flux 2.66s ease-in-out infinite;
}

@keyframes flux {
  0% {
    transform: scale(0.9, 1);
  }
  50% {
    transform: scale(0.8, 1);
  }
  100% {
    transform: scale(0.9, 1);
  }
}
</style>