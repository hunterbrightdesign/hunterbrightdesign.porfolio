<template>
  <div class="about--container flex items-center justify-center flex-wrap content-center py-6 lg:flex lg:flex-nowrap">
    <div class="about--text w-full lg:mr-10 lg:w-3/4">
    <div class="uTxt">0.1
      <span class="font-black text-5xl wTxt ">{{ $t('about.title') }}</span>
    </div>
      <p>
         {{ $t('about.introduction') }} <span class="uTxtPf deco">Fokoui Marco,</span> {{ $t('about.description') }}
      </p>
      <p> {{ $t('about.text-1') }} </p>
      <p>
        {{ $t('about.text-2') }}
      </p>
      <ul class="list--tech list-inside">
        <li v-for="tech in mainTechno" :key="tech.id"><a class="ml-4" :href="tech.uri" target="blank"><span class="deco uTxtPf">{{tech.name}}</span></a></li>
      </ul>
    </div>
    <div class="mt-12 w-full flex flex-nowrap items-center lg:w-1/3">
      <div class="about--detail w-2/3 lg:w-full max-w-xs ">
        <img src="/profile.webp" alt="hunterbrightdesign" min-width="250px" min-height="250px" class="shadow-2xl">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'app',
  data () {
    return {
      mainTechno: [
        {name: 'Javascript (Es6 +)', uri: 'https://www.javascript.com/'},
        {name: 'Vue Js', uri: 'https://vuejs.org/'},
        {name: 'Php (7 +)', uri: 'https://www.javascript.com/'},
        {name: 'Laravel(6 7 8+)', uri: 'https://laravel.com/'},
        {name: 'Postgresql', uri: 'https://www.postgresql.org/'},
        {name:  'Mysql', uri: 'https://www.mysql.com/'},
        {name:  'Nuxtjs', uri: 'https://nuxtjs.org/'},
        {name: 'Node Js', uri: 'https://nodejs.org/'},
      ],
    }
  },
  head() {
    return {
      title: `hunterbrightdesign Portfolio-V2 | ${this.$t('menu.about')}`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'my website description'
        }
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
  $tColor1: #ccd6f6;
  $color: #185a9a;
  $colorTa: #185a9a45;
  .about--container {
    .about--text {
      p { margin: 25px 0; }

      .list--tech {
        list-style-type: "→" !important;
        color: $color;
        display: flex;
        flex-wrap: wrap;

        li {
          width: 49%;

          a {
            display: inline-block;
            width: calc(100% - 50px);
          }

          &::marker {
            display: inline-block;
          }
        }
      }
    }

    .about--detail {
      position: relative;

      img {
        display: block;
        width: 80%;
        margin: 5% auto;
        border-radius: .2rem .8rem;
        cursor: pointer;
        border: solid 1px $color;
        z-index: 2;
        filter: grayscale(.4);

        &:hover {
          filter: grayscale(0);
          transform: scale(1.02) rotate(-1deg);
        }

      }

      &::after, &::before {
        content: "";
        position: absolute;
        z-index: -1;
        width: 80%; height: 90%;
        border-radius: .8rem .2rem;
        border: solid 1px $color;
        background-color: $colorTa;
      }

      &::after {
        top: 0;
        left: 5%;
      }

      &::before {
        bottom: 0;
        right: 5%;
      }
    }
  }
</style>
