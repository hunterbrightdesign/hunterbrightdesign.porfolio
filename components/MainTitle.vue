<template>
  <h3 class="wTxt text-3xl lg:text-5xl font-black mb-10 main--title" :num="num">{{ title }}</h3>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Hello world',
    },
    num: {
      type: String,
      default: '01.'
    }
  },
}
</script>

<style lang="scss" scoped>
  $tColor1: #ccd6f6;
  $color: #185a9a;
  $colorTa: #185a9a;

  .main--title {
    position: relative;
    display: flex;
    align-items: center;
    white-space: nowrap;

    &:before {
      content: attr(num);
      color: $color;
      margin-right: 15px;
      font-weight: normal;
      font-size: 1.1rem;
    }

    &::after {
      content: "";
      display: block;
      background-color: $colorTa;
      width: 100%;
      height: 1px;
      margin-left: 25px;
    }
  }

  @media only screen and (max-width: 768px) {
    .main--title{

      font-size: 1em !important;
    }
  }
</style>

