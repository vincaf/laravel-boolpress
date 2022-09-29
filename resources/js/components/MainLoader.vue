<template>
  <div class="loadingio-spinner-blocks-yq7ofo1vok">
    <div class="ldio-kpv0690zcgc">
      <div style="left: 38px; top: 38px; animation-delay: 0s"></div>
      <div style="left: 80px; top: 38px; animation-delay: 0.125s"></div>
      <div style="left: 122px; top: 38px; animation-delay: 0.25s"></div>
      <div style="left: 38px; top: 80px; animation-delay: 0.875s"></div>
      <div style="left: 122px; top: 80px; animation-delay: 0.375s"></div>
      <div style="left: 38px; top: 122px; animation-delay: 0.75s"></div>
      <div style="left: 80px; top: 122px; animation-delay: 0.625s"></div>
      <div style="left: 122px; top: 122px; animation-delay: 0.5s"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainLoader",
};
</script>

<style lang="scss" scoped>

@keyframes ldio-kpv0690zcgc {
  0% { background: #2c99f4 }
  12.5% { background: #2c99f4 }
  12.625% { background: #aed5f7 }
  100% { background: #aed5f7 }
}
.ldio-kpv0690zcgc div {
  position: absolute;
  width: 40px;
  height: 40px;
  background: #aed5f7;
  animation: ldio-kpv0690zcgc 1s linear infinite;
}
.loadingio-spinner-blocks-yq7ofo1vok {
  width: 200px;
  height: 200px;
  display: inline-block;
  overflow: hidden;
}
.ldio-kpv0690zcgc {
  width: 100%;
  height: 100%;
  position: relative;
  transform: translateZ(0) scale(1);
  backface-visibility: hidden;
  transform-origin: 0 0;
}
.ldio-kpv0690zcgc div { box-sizing: content-box; }
</style>