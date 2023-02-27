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
              <p class="short--descritpion text-white italic text-base ">{{ work.shortDescription }}</p>
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
            <li class="text-sm mr-3"> <a :href="work.uri" target="_blank"><font-awesome-icon :icon="['fa', 'external-link-alt']" /></a> </li>
            <li class="text-sm mr-3" @click="diapoImg(work.listImg, work.nameDetails) "> <font-awesome-icon :icon="['fa', 'align-justify']" /> </li>
            <li class="text-sm"> <a :href="work.github" target="_blank"><font-awesome-icon :icon="['fab', 'github']" /></a> </li>
          </ul>
        </div>
      </div>
    </div>
    <div id="dipo" class="dipo--img animate__animated animate__flipInY " @click="closedipo">
      <h1 class="test"> {{ active }} </h1><hr>
      <span class="closedipo" @click="closedipo"> <font-awesome-icon :icon="['fa', 'times']" /> </span>
      <div class="h-98" >
        <div v-for="li in listImg" :key="li.id" >
          <img :src="li" :alt="active" class="w-3/4 mx-auto my-5">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'app',
  data () {
    return {
      active : null,
      listImg : [0],
      options: {
        slidesPerView: 3,
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      },
      works: [
        {
          name: 'wring',
          img: '/works/testgold.webp',
          uri: 'https://app.wring.dev',
          nameDetails: 'wring for Aichemydev',
          listImg: ['/works/worksDetails/quikly/testgold.webp'],
          github: 'https://github.com/aichemydev/testgold-newui',
          keyword: ['#Test_automation', '#Auto_gen', '#Auto_heal', '#Enhance_coverage'],
          tags: ['VueJs', 'Tornado', 'PostgreSQL', 'Element UI', 'Slack', 'Github', 'Docker', 'kubernetes', 'Azur'],
          description: 'We are a strong technical team comprised of multiple PhDs and Data Science experts. Our founders are established entrepreneurs who have successfully built several products to solve key customer problems. Our people come from top schools like Stanford, Princeton, Johns Hopkins, UT Austin, UC Berkeley, Harvey Mudd, etc. We are comprised of AI experts who are very passionate about solving the problems plaguing testing. We also happen to have several top level chess players in our team attesting to our problem solving capabilities!',
          shortDescription: 'We are a strong technical team comprised of multiple.....',
        },{
          name: 'Bridge Africa',
          img: '/works/worksDetails/Bridge_Africa/bridge_africa.webp',
          uri: 'https://bridgeafrica.com/login',
          nameDetails: 'Bridge_Africa',
          listImg: ['/works/worksDetails/Bridge_Africa/bridge_africa.webp'],
          github: 'https://github.com/hunterbrightdesign',
          keyword: ['#tag1', '#tag2', '#tag3', '#tag4'],
          tags: ['VueJs', 'Laravel', 'Mysql', 'Element UI', 'Trello', 'Github'],
          description: 'Alias error voluptatibus debitis deleniti nesciunt cum tempore quas, neque, vitae eligendi quam magnam nostrum sunt officia molestiae cumque, reprehenderit officiis. Dolorum?',
          shortDescription: 'Alias error voluptatibus debitis deleniti nesciunt cum .....',
        }, {
          name: 'Season',
          img: '/works/season.webp',
          nameDetails: 'Season',
          listImg: ['/works/worksDetails/Season/Season1.webp'],
          uri: 'https://mayem-solutions.com/projets-ms/',
          github: 'https://github.com/hunterbrightdesign',
          keyword: ['#beds24', '#chicApart', '#hosting', '#accomodations', '#booking'],
          tags: ['VueJs', 'Laravel', 'PostgreSQL', 'Element UI', 'Trello', 'Gitlab', 'Flutter'],
          description: 'Season is a web application allowing the Chicaparts company on the one hand to have an ERP for the internal planning of all of its furnished rental management activities, on the other hand to update a web extranet available to its customers',
          shortDescription: 'Season is a web application allowing the Chicaparts.....',
        }, {
          name: 'Stratochange',
          img: '/works/stratochange.webp',
          uri: 'http://stratochange-nuxt.herokuapp.com/',
          nameDetails: 'Stratochange',
          listImg: ['/works/worksDetails/Stratochange/Stratochange1.webp'],
          github: 'https://github.com/hunterbrightdesign',
          keyword: ['#change', '#stakholder', '#priorisations', '#risks'],
          tags: ['VueJs', 'Nuxtjs', 'c#', 'Tailwind Css','Microsoft Azure', 'Flutter'],
          description: 'While most projects produce significant outputs, the expected changes in the medium and long term are often not forthcoming. The major cause of this insufficiency is the lack of participation and ownership of the project by its stakeholders. </br>This low participation can be greatly improved thanks to our operational strategic change management tools: STRAT-O-CHANGE',
          shortDescription: 'This low participation can be greatly improved thanks to .....',
        }, {
          name: 'Argon',
          img: '/works/argon.webp',
          uri: 'https://mvengi.com/',
          nameDetails: 'Argon',
          listImg: ['/works/worksDetails/Argon/Argon1.webp',],
          github: 'https://github.com/hunterbrightdesign',
          keyword: ['#shool management system', '#education', '#learn'],
          tags: ['Laravel', 'Mysql', 'Html/css', 'jQuery', 'cpanel'],
          description: 'All-in-one school software package, the complete private and public school management solution Modern school management platform on the move',
          shortDescription: 'All-in-one school software package, the .....',
        }, {
          name: 'Easy Gest',
          img: '/works/easygest.webp',
          uri: 'https://github.com/hunterbrightdesign',
          nameDetails: 'Easy_Gest',
          listImg: ['/works/worksDetails/Easy_Gest/Easy_Gest1.webp'],
          github: 'https://github.com/hunterbrightdesign',
          keyword: ['#management', '#Human resources', '#Accounting', '#messaging'],
          tags: ['VueJs', 'Laravel', 'MYSQL', 'Bootstrap', 'Trello', 'Gitlab'],
          description: 'Fully human resources & accounting application with lot of functionalities',
          shortDescription: 'Fully human resources & accounting ......',
        },
      ],
      activatedWork: undefined,
      loading: false,
    }
  },
  head() {
    return {
      title: `hunterbrightdesign Portfolio-V2 | ${this.$t('menu.work')}`,
      meta: [
        {
          hid: 'description',
          name: 'hunterbrightdesign',
          content: 'Software Engineer'
        }
      ],
    }
  },
  methods: {
    diapoImg(e , s) {
      console.log(e , s)
      this.listImg = e
      this.active = s
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
      position: fixed;
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
        margin-bottom: 3vh;
        z-index: 9;
      }
      .h-98{
        height: 86vh;
        overflow: auto;
        margin-top: 3vh;
        margin-bottom: 5vh;
      }
      .test{
        font-size: 50px;
        margin-top: 5vh;
        margin-bottom: 2vh;
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
