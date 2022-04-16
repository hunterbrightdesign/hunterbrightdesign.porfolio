<template>
  <div class="skill--container flex items-center justify-center flex-wrap content-center py-6 lg:flex lg:flex-nowrap">
    <div class="work--timeline lg:mr-10 w-full lg:w-3/4">
      <MainTitle :title="$t('skills.title')" num="0.2" />
      <div class="wt--container">
        <div v-for="exp in $t('skills.experiences')" :key="exp.id" class="wt--item">
         <!-- {{ $t('skills.experiences') }} -->
         <div class="wti--icon" color="#900" :style="{ borderColor: exp.color}">
            <a :href="exp.uri"><img :src="exp.logo" :alt="exp.enterprise" target="_blank" width="50px" height="50px"></a>
          </div>
          <div class="wti--desc">
            <div class="wtid--content">
              <h3 :style="{ color: exp.color}">{{ exp.role }}</h3>
              <h3 class="font-thin text-sm italic" :style="{ color: exp.colorTa}">From <span class="underline cursor-pointer">{{ exp.from }}</span> to <span class="underline cursor-pointer">{{ exp.to }}</span></h3>
              <p class="mt-6 text-base divide-y">{{ exp.description }}</p>
              <div class="divider my-3" :style="{ backgroundColor: exp.colorTa}"></div>
              <ul class="text-xs font-bold" :style="{ color: exp.colorTa}">
                <li v-for="tag in exp.tags" :key="tag.id" class="deco">{{tag}}</li>
              </ul>
            </div>
            <div class="wtid--aside font-thin text-sm" :style="{ backgroundColor: exp.color}">
              <a :href="exp.uri">{{ exp.enterprise }}</a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="skill--list w-full lg:w-1/4">
      <div v-for="skill in skills" :key="skill.id" class="sl--item font-thin text-sm font-bold text-1xl">
        <a :href="skill.uri" target="blank " class="">{{ skill.elt}}</a>
        <div class="sl--value" :style="{ width: skill.value}"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'app',
  data () {
    return {
      skills: [
        { elt: 'Laravel(6 7 8+)', value: '90%', uri: 'https://laravel.com/' },
        { elt: 'php (8+)', value: '95%', uri: 'https://www.php.org/' },
        { elt: 'Python', value: '50%', uri: 'https://python.org/' },
        { elt: 'Django', value: '50%', uri: 'https://djangoproject.com/' },
        { elt: 'Torbado/Flask', value: '50%', uri: 'https://flask.palletsprojects.com/en/2.1.x/' },
        { elt: 'Postgresql / Mysql / Sqlite', value: '90%', uri: '#' },
        { elt: 'Vue Js', value: '50%', uri: 'https://vuejs.org/' },
        { elt: 'Nuxtjs', value: '50%', uri: 'https://nuxtjs.org/' },
        { elt: 'Javascript Es6+', value: '60%', uri: 'https://www.javascript.com/' },
        { elt: 'Git / Github ', value: '87%', uri: 'https://github.com/hunterbrightdesign' },
        { elt: 'Docker / Kubernetes ', value: '40%', uri: 'https://www.docker.com/' },
        { elt: 'Wordpress', value: '98%', uri: 'https://wordpress.com/' },
      ]
    }
  },
  head() {
    return {
      title: `hunterbrightdesign Portfolio-V2 | ${this.$t('menu.skills')}`,
      meta: [
        {
          hid: 'description',
          name: 'hunterbrightdesign',
          content: 'developpeur fullstack php python'
        }
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
  $tColor1: #ccd6f6;
  $tColor2: #28375f;
  $color: #185a9a;
  $bg--dark: #091320;
  $colorTa: #28375f;

  .skill--container {
    .work--timeline {
      .wt--container {
        max-height: 60vh;
        overflow-y: scroll;
        scrollbar-width: none;  /* Firefox */

        &::-webkit-scrollbar {
          -ms-overflow-style: none;  /* IE and Edge */
          display: none;
        }

        &::-moz-scrollbar {
          display: none;
        }

        .wt--item {
          display: flex;
          flex-wrap: nowrap;
          align-items: center;
          justify-content: space-between;
          margin: 3vh 0;
          position: relative;

          .wti--desc {
            width: 85%;
            border-radius: .2rem .9rem .2rem .2rem;
            background-color: #fff;
            box-shadow: 0 30px 60px -12px rgba(50, 50, 93, 0.25), 0 18px 36px -18px rgba(0, 0, 0, 0.3), 0 -12px 36px -8px rgba(0, 0, 0, 0.025);
            display: flex;
            align-items: center;
            justify-content: space-between;
            overflow: hidden;
            position: relative;
            // height: 200px;

            .wtid--content {
              padding: 1rem;
              width: 80%;

              .divider {
                height: 1px;
              }

              ul {
                display: flex;

                li {
                  margin-right: .5rem;
                }
              }
            }

            .wtid--aside {
              width: 20%;
              height: 100%;
              color: #fff;
              position: absolute;
              top: 0; right: 0;
              display: flex;
              align-items: center;
              justify-content: center;
              text-align: center;

            }
          }

          .wti--icon {
            width: 7vh; height: 7vh;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #fff;
            box-shadow: 0 30px 60px -12px rgba(50, 50, 93, 0.25), 0 18px 36px -18px rgba(0, 0, 0, 0.3), 0 -12px 36px -8px rgba(0, 0, 0, 0.025);
            position: relative;
            border: solid;
            padding: .6rem;

            img {
              height: 70%;
              border-radius: 50%;
            }

            &::before {
              content: "";
              position: absolute;
              height: 1px;
              width: 200px;
              background-color: #fff;
              z-index: -1;
              // right: 50%;
            }

            &::after {
              content: "";
              position: absolute;
              width: 1px;
              height: calc(4vh + 150px);
              background-color: #fff;
              z-index: -1;
              top: 50%;
            }
          }
          &:nth-child(2n + 1) {
            flex-direction: row-reverse;

            .wti--desc {
              flex-direction: row-reverse;

              .wtid--aside {
                left: 0;
              }
            }

            .wti--icon {

              &::before {
                // left: 50%;
              }

              &::after {
                top: 50%;
              }
            }
          }

          &:last-child {
            .wti--icon {
              &::after {
                display: none;
                height: 0; width: 0;
              }
            }
          }
        }
      }
    }

    .skill--list {
      .sl--item {
        position: relative;
        width: 100%;
        margin: 1.5rem 0;
        color: $tColor2;

        &::before {
          content: "";
          width: 100%;
          height: 2px;
          position: absolute;
          bottom: -.4rem;
        }

        .sl--value {
          position: absolute;
          bottom: -.4rem;
          height: 2px;
          background-color: $color;
        }
      }
    }
  }

  @media only screen and (max-width: 768px){
          .wt--item{
            display: block !important;
          }

          .wti--icon{
            margin-left: auto;
            margin-right: auto;
            &::before {
              display: none;
            }
          }
          .wti--desc{
            width: 99% !important;
          }
  }
</style>


