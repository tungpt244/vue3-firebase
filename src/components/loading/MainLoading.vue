<template>
  <div class="main-loading">
    <div class="loading">
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>
</template>
<style scoped>
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(200deg, #f4efef, #e3eeff);
}

.main-loading {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  z-index: 10;
}

.loading {
  width: 100px;
  height: 100px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  transform: rotate(45deg);
}
.loading span {
  flex-shrink: 0;
  width: 30%;
  height: 30%;
  --c: gray;
  background-color: var(--c);
  position: relative;
  transform: scale(0);
  animation: blinking 2s linear infinite;
  animation-delay: var(--d);
}
.loading span::before {
  position: absolute;
  width: 100%;
  height: 100%;
  text-align: center;
  transform: rotate(-45deg);
}
.loading span:nth-child(7) {
  --c: #f15a5a;
  --d: 0s;
}
.loading span:nth-child(4),
.loading span:nth-child(8) {
  --c: #f0c419;
  --d: 0.2s;
}
.loading span:nth-child(1),
.loading span:nth-child(5),
.loading span:nth-child(9) {
  --c: #4eba6f;
  --d: 0.4s;
}
.loading span:nth-child(2),
.loading span:nth-child(6) {
  --c: #2d95bf;
  --d: 0.6s;
}
.loading span:nth-child(3) {
  --c: #955ba5;
  --d: 0.8s;
}
@keyframes blinking {
  0%,
  100% {
    transform: scale(0);
  }
  40%,
  80% {
    transform: scale(1);
  }
}
</style>
