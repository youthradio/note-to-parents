<template>
  <div class="container">
    <HeaderContainer />
    <article>
      <p>
        {{ articleData.opening }}
      </p>

      <ScenarioContainer
        v-for="(scenario,index) in articleData.scenarios"
        :key="`${scenario.title}-${index}`"
        :scenario="scenario"
      />
      <div
        role="credits"
        class="credits"
      >
        <strong>Credits: </strong>{{ articleData.credits }}
      </div>
      <div
        role="credits"
        class="credits"
      >
        <strong>Acknowledgments: </strong> <span v-html="articleData.thanks" />
      </div>
    </article>
    <ShareContainer />
    <RelatedPostsContainer />
    <FooterContainer />
  </div>
</template>

<script>

import CommonUtils from '../mixins/CommonUtils'
import ArticleData from '../data/data.json'
import RelatedPostsContainer from '~/components/RelatedPosts/RelatedPostsContainer'
import HeaderContainer from '~/components/Header/HeaderContainer'
import ScenarioContainer from '~/components/Custom/ScenarioContainer'
import ShareContainer from '~/components/Custom/ShareContainer'
import FooterContainer from '~/components/Footer/FooterContainer'

export default {
  components: {
    RelatedPostsContainer,
    HeaderContainer,
    ShareContainer,
    ScenarioContainer,
    FooterContainer
  },
  mixins: [
    CommonUtils
  ],
  data () {
    return {
    }
  },
  computed: {

  },
  watch: {

  },
  asyncData (ctx) {
    return {
      articleData: ArticleData.content
    }
  },
  mounted () {
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
@import "~@/css/vars";
@import "~@/css/base";

.credits {
  font-size: 0.8rem;
  margin-top: 1rem;
}
</style>
