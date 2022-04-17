<template>
  <div class="app-social fixed hidden sm:flex flex-col items-center justify-between mx-12">
    <div class="as--list">
      <ul>
        <li v-for="social in socials" :key="social.id" class="my-3 uTxtTa">
          <a :href="social.uri" class="text-lg asl--uri" target="blank">
            <font-awesome-icon :icon="['fab', social.icon]" />
          </a>
        </li>
      </ul>
    </div>
    <div class="as--line mt-4"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      socials: [
        { label: 'Github', icon: 'github', uri: 'https://github.com/hunterbrightdesign' },
        { label: 'LinkedIn', icon: 'linkedin', uri: 'https://www.linkedin.com/in/hunterbrightdesign' },
        { label: 'Telegram', icon: 'telegram-plane', uri: 'https://t.me/hunterbrightdesign' },
        { label: 'Codepen', icon: 'codepen', uri: 'https://codepen.io/hunterbrightdesign' },
        { label: 'twitter', icon: 'twitter', uri: 'https://twitter.com/FokouiM' },
        { label: 'Whatsapp', icon: 'whatsapp', uri: 'https://wa.me/237697040726' },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  $colorTa: #185a9a;
  $color: #185a9a;
  $colorovsocial:#185a9a45;

  .app-social {
    z-index: 1;
    left: 0; bottom: 0;

    .as--list {
      display: flex;
      flex-direction: column;
      align-items: center;

      .asl--uri {
        display: inline-block;
        color: $color;

        &:hover {
          transform: scale(1.5);
          color: $colorovsocial;
        }
      }
    }

    .as--line {
      height: 10vh;
      width: 1px;
      background-color: $colorTa;
    }
  }
</style>

