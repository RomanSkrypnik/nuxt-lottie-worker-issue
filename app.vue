<template>
  <div ref="containerRef" />
</template>
<script setup>
import lottie from 'lottie-web/build/player/lottie_light';

const containerRef = shallowRef();

onMounted(async () => {
  lottie.useWebWorker(true); // if you comment this line - animation will play in dev and build modes

  const animationData = {
    container: containerRef.value,
    renderer: 'svg',
    loop: true,
    autoplay: true,
    path: 'https://assets1.lottiefiles.com/datafiles/HN7OcWNnoqje6iXIiZdWzKxvLIbfeCGTmvXmEm1h/data.json',
  };

  lottie.loadAnimation(animationData);
});
</script>
