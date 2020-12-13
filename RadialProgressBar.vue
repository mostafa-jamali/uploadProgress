<template>
  <svg class="radial-progressbar" viewBox="0 0 100 100">
    <defs>
      <linearGradient
        :id="`circle-progress-gradient-${title}`"
        x1="0%"
        y1="0%"
        x2="100%"
        y2="0%"
      >
        <stop offset="0%" :style="`stop-color:${startColor};stop-opacity:1`" />
        <stop offset="100%" :style="`stop-color:${endColor};stop-opacity:1`" />
      </linearGradient>
    </defs>
    <circle
      cx="50"
      cy="50"
      r="45"
      :stroke="`url(#circle-progress-gradient-${title})`"
      stroke-width="10"
      stroke-dasharray="283"
      :stroke-dashoffset="283 - (value / total) * 283"
      fill="transparent"
    />
  </svg>
</template>

<script>
export default {
  name: "RadialProgressBar",
  props: {
    title: "",
    value: "",
    total: "",
    startColor: "",
    endColor: "",
  },
};
</script>

<style lang="scss" scoped>
.radial-progressbar {
  background-color: transparent;
  // position: absolute;
  // top: -15px;
  // left: -15px;
  width: 25px;
  height: 25px;
  transform: rotate(-90deg);
  z-index: 26;
  user-select: none;
  pointer-events: none;

  circle {
    transition: 0.1s;
  }
}
</style>
