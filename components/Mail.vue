<template>
  <div class="app-mail fixed hidden sm:flex flex-col items-center justify-between mx-12">
      <p class="mail-content uTxt text-base font-bold text-lg"><a :href="`mailto:${mail}?subject= Contact from : Portfolio`">{{ mail }}</a></p>
    <div class="mail--line mt-4"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      mail: 'fokoui-maco@hunter-tech.tech'
    }
  },
}
</script>

<style lang="scss" scoped>
  $tColor1: #ccd6f6;
  $color: #185a9a;
  $colorTa: #f2680045;

  .app-mail {
    right: 0; bottom: 0;
    z-index: 2;

    .mail-content {
      writing-mode: vertical-rl;
      text-orientation: mixed;
      cursor: pointer;
      text-shadow: 1 1 3px #111;

      &:hover {
        transform: translateY(-5px);
        color: $tColor1;
      }

      &:hover+.mail--line {
        background-color: $tColor1;
      }
    }

    .mail--line {
      height: 10vh;
      width: 1px;
      background-color: $color;
    }
  }
</style>

