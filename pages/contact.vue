<template>
  <div class="contact--container">
    <h4 class="subtitle uTxt my-3">
      <span class="text-base uTxt font-thin">04.</span>
      {{ $t('contact.title') }}
    </h4>
    <h3 class="font-black text-4xl md:text-6xl cTitle text-center">{{ $t('contact.introduction') }}</h3>
    <p class="my-8 leading-relaxed text-center font-thin">
      {{ $t('contact.description') }}
    </p>
    <div>
      <span>
        <a :href="`mailto:${mail}?subject= Contact from : Portfolio V2`" class="bp-btn px-2.5 py-2">
          <font-awesome-icon :icon="['fa', iconEmail]" />

        </a>
      </span>
      <span v-for="social in socials" :key="social.id" class="">
        <a :href="social.uri" class="text-lg asl--uri bp-btn px-3 py-2 m-2" target="blank">
          <font-awesome-icon :icon="['fab', social.icon]" />
        </a>
      </span>
      </div>
  </div>
</template>

<script>
export default {
  layout: 'app',
  data () {
    return {
      mail: 'hunterbrightdesign@hotmail.com',
      iconEmail:'envelope',
      socials: [
        { label: 'Telegram', icon: 'telegram-plane', uri: 'https://t.me/hunterbrightdesign' },
        { label: 'Whatsapp', icon: 'whatsapp', uri: 'https://wa.me/237697040726' },
      ]

    }
  },
  head() {
    return {
      title: `hunterbrightdesign Portfolio-V2 | ${this.$t('menu.contact')}`,
      meta: [
        {
          hid: 'description',
          name: 'hunterbrightdesign',
          content: 'Software Engineer'
        }
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
  $color: #f26800;
  .contact--container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    p {
      width: 60%;
    }

    .divider {
      width: 7%;
      height: 1px;
      background-color: $color;
    }
  }
</style>
