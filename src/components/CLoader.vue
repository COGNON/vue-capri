<template>
  <div class="flex flex-column justify-center">
    <div class="loader rounded-full w-5 h-5 border-2 border-gray-400 border-t-black" />
  </div>
</template>

<style scoped>
.loader {
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
