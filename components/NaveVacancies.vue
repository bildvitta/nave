<template>
  <nave-intersect :root-margin="rootMargin" @~enter="onEnter('vacancies')">
    <section id="vacancies" class="bg-primary nave-vacancies py-12">
      <h2 class="font-bold leading-none mb-16 md:text-5xl sm:text-4xl text-3xl text-center text-white">Embarque na Nave</h2>
      <div v-if="renders.vacancies" class="overflow-hidden">
        <nave-slider>
          <nave-card v-for="(vacancie, index) in vacanciesList" :key="index" class="nave-vacancies__card" classes="w-64 sm:w-350" :content="vacancie" />
        </nave-slider>
      </div>
    </section>
  </nave-intersect>
</template>

<script>
import intersect from '../mixins/intersect'
import naveIntersect from './NaveIntersect'

const vacancies = [
  {
    title: 'php',
    resume: 'backend ',
    description: 'é simplesmente uma simulação de texto da indústria tipográfica e de impressos, e vem sendo utilizado desde o século XVI, quando um.modelos de tipos.',
    img: require('../assets/img/PHP-logo.png')
  },
  {
    title: 'Rubi on Rails',
    resume: ' backend',
    description: 'é simplesmente uma simulação de texto da indústria tipográfica e de impressos, e vem sendo utilizado desde o século XVI, quando um.modelos de tipos.',
    img: require('../assets/img/Ruby_On_Rails_Logo.png')
  },
  {
    title: 'VUE.JS',
    resume: ' Frontend',
    description: 'é simplesmente uma simulação de texto da indústria tipográfica e de impressos, e vem sendo utilizado desde o século XVI, quando um.modelos de tipos.',
    img: require('../assets/img/vuejs.png')
  },
  {
    title: 'php',
    resume: 'Test',
    description: 'é simplesmente uma simulação',
    img: require('../assets/img/PHP-logo.png')
  }
]

export default {
  components: {
    naveIntersect
  },

  mixins: [
    intersect
  ],

  computed: {
    vacanciesList () {
      return vacancies
    }
  }
}
</script>

<style lang="scss">
.nave-vacancies {
  &__card {
    min-height: 420px;

    &:last-child {
      padding-right: 20px;
    }

    & + & {
      margin-left: 90px;
    }
  }

  @media screen and (max-width: 640px) {
    &__card + &__card {
      margin-left: 30px;
    }
  }
}
</style>
