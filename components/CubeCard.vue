<template>
  <div class="flex items-center justify-center">
    <div class="cube-container">
      <div class="scene">
        <div class="cube">
          <div class="cube-face cube-face--front"></div>
          <div class="cube-face cube-face--back"></div>
          <div class="cube-face cube-face--right"></div>
          <div class="cube-face cube-face--left"></div>
          <div class="cube-face cube-face--top"></div>
          <div class="cube-face cube-face--bottom"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cube-container {
  position: relative;
  width: 280px;
  height: 280px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--surface);
  border: 1px solid rgba(140, 150, 170, 0.2);
  border-radius: 12px;
  box-shadow: 
    0 8px 32px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
}

.scene {
  width: 220px;
  height: 220px;
  perspective: 800px;
}

.cube {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  animation: rotate 28s linear infinite;
}

@media (prefers-reduced-motion: reduce) {
  .cube {
    animation: none;
  }
}

@keyframes rotate {
  from {
    transform: rotateX(0deg) rotateY(0deg);
  }
  to {
    transform: rotateX(360deg) rotateY(360deg);
  }
}

.cube-face {
  position: absolute;
  width: 220px;
  height: 220px;
  border: 2px solid rgba(140, 150, 170, 0.4);
  opacity: 0.75;
  backdrop-filter: blur(10px);
}

.cube-face--front {
  background: linear-gradient(135deg, rgba(140, 150, 170, 0.3), rgba(100, 110, 140, 0.2));
  transform: rotateY(0deg) translateZ(110px);
}

.cube-face--back {
  background: linear-gradient(135deg, rgba(100, 110, 140, 0.3), rgba(140, 150, 170, 0.2));
  transform: rotateY(180deg) translateZ(110px);
}

.cube-face--right {
  background: linear-gradient(135deg, rgba(140, 150, 170, 0.25), rgba(100, 110, 140, 0.25));
  transform: rotateY(90deg) translateZ(110px);
}

.cube-face--left {
  background: linear-gradient(135deg, rgba(100, 110, 140, 0.25), rgba(140, 150, 170, 0.25));
  transform: rotateY(-90deg) translateZ(110px);
}

.cube-face--top {
  background: linear-gradient(135deg, rgba(140, 150, 170, 0.2), rgba(100, 110, 140, 0.3));
  transform: rotateX(90deg) translateZ(110px);
}

.cube-face--bottom {
  background: linear-gradient(135deg, rgba(100, 110, 140, 0.2), rgba(140, 150, 170, 0.3));
  transform: rotateX(-90deg) translateZ(110px);
}
</style>
