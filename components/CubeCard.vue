<template>
  <div class="flex items-center justify-center pt-8 pb-4 sm:pt-12 md:pt-8">
    <div
      class="cube-container"
      @mousedown="startDrag"
      @touchstart="startDrag"
      @mousemove="onDrag"
      @touchmove="onDrag"
      @mouseup="endDrag"
      @touchend="endDrag"
      @mouseleave="endDrag"
    >
      <div class="scene">
        <div
          class="cube"
          :class="{ dragging: isDragging }"
          :style="{ transform: currentTransform }"
        >
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

<script setup>
import { ref, computed } from "vue";

const isDragging = ref(false);
const startX = ref(0);
const startY = ref(0);
const rotationX = ref(0);
const rotationY = ref(0);
const currentRotationX = ref(0);
const currentRotationY = ref(0);

const currentTransform = computed(() => {
  if (isDragging.value) {
    return `rotateX(${currentRotationX.value}deg) rotateY(${currentRotationY.value}deg)`;
  }
  return "";
});

const startDrag = (e) => {
  isDragging.value = true;
  const clientX = e.touches ? e.touches[0].clientX : e.clientX;
  const clientY = e.touches ? e.touches[0].clientY : e.clientY;

  startX.value = clientX;
  startY.value = clientY;
  rotationX.value = currentRotationX.value;
  rotationY.value = currentRotationY.value;
};

const onDrag = (e) => {
  if (!isDragging.value) return;

  e.preventDefault();
  const clientX = e.touches ? e.touches[0].clientX : e.clientX;
  const clientY = e.touches ? e.touches[0].clientY : e.clientY;

  const deltaX = clientX - startX.value;
  const deltaY = clientY - startY.value;

  currentRotationX.value = rotationX.value - deltaY * 0.5;
  currentRotationY.value = rotationY.value + deltaX * 0.5;
};

const endDrag = () => {
  isDragging.value = false;
};
</script>

<style scoped>
.cube-container {
  position: relative;
  width: 180px;
  height: 180px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--surface);
  border: 1px solid rgba(120, 140, 255, 0.2);
  border-radius: 12px;
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  cursor: grab;
  user-select: none;
  touch-action: none;
}

.cube-container:active {
  cursor: grabbing;
}

.scene {
  width: 160px;
  height: 160px;
  perspective: 800px;
  pointer-events: none;
}

.cube {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  animation: rotate 32s linear infinite;
  transition: transform 0.1s ease-out;
}

.cube.dragging {
  animation: none;
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
  width: 160px;
  height: 160px;
  border: 2px solid var(--accent);
  opacity: 0.75;
  backdrop-filter: blur(10px);
}

.cube-face--front {
  background: linear-gradient(
    135deg,
    rgba(110, 168, 255, 0.3),
    rgba(58, 92, 255, 0.2)
  );
  transform: rotateY(0deg) translateZ(80px);
}

.cube-face--back {
  background: linear-gradient(
    135deg,
    rgba(58, 92, 255, 0.3),
    rgba(110, 168, 255, 0.2)
  );
  transform: rotateY(180deg) translateZ(80px);
}

.cube-face--right {
  background: linear-gradient(
    135deg,
    rgba(110, 168, 255, 0.25),
    rgba(58, 92, 255, 0.25)
  );
  transform: rotateY(90deg) translateZ(80px);
}

.cube-face--left {
  background: linear-gradient(
    135deg,
    rgba(58, 92, 255, 0.25),
    rgba(110, 168, 255, 0.25)
  );
  transform: rotateY(-90deg) translateZ(80px);
}

.cube-face--top {
  background: linear-gradient(
    135deg,
    rgba(110, 168, 255, 0.2),
    rgba(58, 92, 255, 0.3)
  );
  transform: rotateX(90deg) translateZ(80px);
}

.cube-face--bottom {
  background: linear-gradient(
    135deg,
    rgba(58, 92, 255, 0.2),
    rgba(110, 168, 255, 0.3)
  );
  transform: rotateX(-90deg) translateZ(80px);
}
</style>
