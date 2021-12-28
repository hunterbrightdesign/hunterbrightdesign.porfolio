<template>
  <div class="work--container overflow-hidden py-6 flex-col items-center justify-center flex-wrap content-center">
    <div class="w-full">
      <MainTitle title="Some things I've build" num="0.3" />
      <div class="wc--container flex items-center justify-center flex-wrap">
        <div v-for="work in works" :key="work.id" class="wc--item animate__animated animate__fadeIn">
          <div class="wi--img">
            <img :src="work.img" :alt="work.name" min-width="400px" min-height="190px">
          </div>
          <div class="wi--content">
            <div class="wic--elt">
              <h3 class="wic--title text-3xl text-white font-black text-center">{{ work.name }}</h3>
              <div class="short--divider my-3"></div>
              <p class="short--descritpion uTxt italic text-base ">{{ work.shortDescription }}</p>
              <ul class="text-xs font-thin uTxtTa2 list colorwhiet">
                <li v-for="tag in work.keyword" :key="tag.id" class="deco">{{tag}}</li>
              </ul>
            </div>
          </div>
          <div class="wi--details animate__animated animate__delay-slow animate__flipInY">
            <div class="wid--container p-3 font-thin text-base">
              <p class="text-center overflow-hidden colorwhiet">{{ work.description}}</p>
              <div class="divider my-5"></div>
              <ul class="text-xs font-bold uTxtTa colorwhiet">
                <li v-for="tag in work.tags" :key="tag.id" class="deco">{{tag}}</li>
              </ul>
            </div>
          </div>
          <ul class="wic--links">
            <li class="text-sm mr-3"> <a :href="work.uri"><font-awesome-icon :icon="['fa', 'external-link-alt']" /></a> </li>
            <li class="text-sm mr-3" @click="diapoImg(work.nameDetails), active = work.nameDetails "> <font-awesome-icon :icon="['fa', 'align-justify']" /> </li>
            <li class="text-sm"> <a :href="work.github"><font-awesome-icon :icon="['fab', 'github']" /></a> </li>
          </ul>
        </div>
      </div>
    </div>
    <div id="dipo" class="dipo--img animate__animated animate__flipInY">
      <span class="closedipo" @click="closedipo"> <font-awesome-icon :icon="['fa', 'times']" /> </span>
      <h1 class="test"> {{ active }}  </h1>
      <p class="test text-sm ">encore de conception ......</p>

    </div>
  </div>
</template>

<script>
export default {
  layout: 'app',
  data () {
    return {
      active : null,
      works: [
        {
          name: 'Bridge Africa',
          img: '/works/workerly.webp',
          uri: '#',
          nameDetails: 'Bridge_Africa',
          github: 'Bridge_Africa',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'Mysql', 'Element UI', 'Trello', 'Github'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        }, {
          name: 'Season',
          img: '/works/season.webp',
          nameDetails: 'Season',
          uri: '#',
          github: '#',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        }, {
          name: 'Stratochange',
          img: '/works/stratochange.webp',
          uri: '#',
          nameDetails: 'Stratochange',
          github: '#',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        }, {
          name: 'Argon',
          img: '/works/argon.webp',
          uri: '#',
          nameDetails: 'Argon',
          github: '#',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        }, {
          name: 'Easy Gest',
          img: '/works/easygest.webp',
          uri: '#',
          nameDetails: 'Easy_Gest',
          github: '#',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        }, {
          name: 'Van Internationnal App',
          img: '/works/van_international.webp',
          uri: '#',
          nameDetails: 'Van_Internationnal_App',
          github: '#',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Lorem ipsum dolor sit amet consectum',
        },
      ],
      activatedWork: undefined,
      loading: false,
      selectImgWork:{
        Bridge_Africa: ['L1.webp','L2.webp,L3.webp','L4.webp'],
        Season: ['L1.webp','L2.webp,L3.webp','L4.webp'],
        Stratochange: ['L1.webp','L2.webp,L3.webp','L4.webp'],
        Argon: ['L1.webp','L2.webp,L3.webp','L4.webp'],
        Easy_Gest: ['L1.webp','L2.webp,L3.webp','L4.webp'],
        Van_Internationnal_App: ['L1.webp','L2.webp,L3.webp','L4.webp'],
      }
    }
  },
  head() {
    return {
      title: `hunterbrightdesign Portfolio-V2 | ${this.$t('menu.work')}`,
      meta: [
        {
          hid: 'description',
          name: 'hunterbrightdesign',
          content: 'developpeur fullstack php python'
        }
      ],
    }
  },
  methods: {
    diapoImg(e) {
      console.log(e)
      const cv = document.getElementById('dipo')
      cv.style.display = 'block'
    },
    closedipo() {
      const cv = document.getElementById('dipo')

      cv.classList.remove('animate__flipInY')
      cv.classList.add('animate__flipOutY')

      setTimeout(() => {
        cv.style.display = 'none'
        cv.classList.remove('animate__flipOutY')
        cv.classList.add('animate__flipInY')
      }, 750)
    },
  }
}
</script>

<style lang="scss" scoped>
  $tColor1: #ccd6f6;
  $tColor2: #8892b0;
  $color: #185a9a;
  $colorTa: #f2680045;
  $colorTa2: #f2680099;
  $bg--dark: #011b3d;
  $bg: #0a192f;
  $bgTa: #0a192fcc;
  $bgTa2: #0a192f99;

  .work--container {
    display: flex;
    align-items: center;

    .wc--container {

      &::-webkit-scrollbar {
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
        display: none;
      }

      .wc--item {
        margin-bottom: 3vh;
        overflow: hidden;
        border-radius: .4rem;
        position: relative;

        .wi--img {
          height: 100%;

          img {
            height: 100%;
          }
        }

        .wi--content {
          position: absolute;
          top: 0; left: 0;
          width: 100%; height: 100%;
          background-color: $bgTa;
          display: flex;
          flex-direction: column;
          align-items: left;
          justify-content: space-between;

          .wic--elt {
            display: flex;
            flex-direction: column;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            height: 100%;
            transition: all .8s ease-in;

            .short--divider {
              width: 10%;
              height: 1px;
              background-color: $color;
            }
          }

        }

        .wi--details {
          position: absolute;
          top: 12%; left: 7%;
          width: 86%;
          height: 76%;
          border: solid 1px $color;
          border-radius: 5px 12px;
          display: none;

          .wid--container {
            width: calc(100% - 10px); height: calc(100% - 10px);
            background-color: $bg--dark;
            border: solid 1px $colorTa;
            margin: 5px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border-radius: 5px 8px;

            .divider {
              height: 1px;
              width: 80%;
              background-color: $colorTa;
            }

            ul {
              display: flex;
              // color: $tColor1;

              li {
                margin-right: .5rem;
              }
            }
          }
        }

        .wic--links {
          position: absolute;
          bottom: 10px; left: 0;
          height: 10%;
          width: auto;
          display: flex;
          align-items: center;
          color: #fff;
          background-color: $color;
          padding: 20px 10px;
          border: solid 1px #fff;
          border-left: solid 6px $bg;
          border-radius: 0 .3rem .3rem 0;

          li {
            &:hover {
              color: $bg--dark;
              transition: all .15s ease-in-out;
              transform: scale(1.05);
            }
          }
        }

        &:hover {
          border: solid 1px $color;

          .wi--img {
            transform: scale(1.04) rotate(.5deg);
          }

          .wi--content {
            background-color: $bgTa2;

            .wic--elt {
              transition: all .6s ease-in;
              transform: translateY(-150%);
            }
          }

          .wi--details {
            display: block;
          }
        }
      }
    }
  }
  .colorwhiet{
        color: #ccd6f6;
      }
    .dipo--img{
      display: none;
      position: absolute;
      top: 0;
      width: 100%;
      height: 100vh;
      background: #011736ce;
      z-index: 9;
      .closedipo{
        position: absolute;
        right: 50%;
        color:$tColor1 ;
        background: $color;
        padding: 5px;
        text-align: center;
        width: 35px;
        height: 35px;
        border-radius: 49%;
        border: solid 1px #fff;
        cursor: pointer;
        z-index: 9;
      }
      .test{
        font-size: 50px;
        margin-top: 15vh;
        color: #fff;
        text-align: center;
      }
    }

  @media (min-width: '1280px') {
    .wc--container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;

      .wc--item {
        width: calc(50% - 10px) !important;
      }
    }
  }
</style>
