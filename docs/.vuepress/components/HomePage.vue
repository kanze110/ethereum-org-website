<template>
  <div>
    <div class="headline-text-container">
      <h1 class="headline-title">{{ translateString('page-home-title') }}</h1>
      <div class="headline-subtitle">
        {{ translateString('page-home-subtitle') }}
      </div>
      <router-link
        :to="langPath() + 'what-is-ethereum/'"
        class="button headline-button"
        >{{ translateString('learn-more') }}</router-link
      >
    </div>

    <div class="intro-blocks">
      <div class="intro-block" v-if="isEnglish">
        <h3 class="header">
          <span class="arrow">→</span
          >{{ translateString('page-home-section-individuals-title') }}
        </h3>
        <ul>
          <li class="highlight highlight-small">
            <router-link :to="langPath() + 'what-is-ethereum/'" class="black">
              {{ translateString('page-home-section-individuals-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link :to="langPath() + 'dapps/'" class="black">
              {{ translateString('page-home-section-individuals-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link :to="langPath() + 'learn/'" class="black">
              {{ translateString('page-home-section-individuals-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="langPath() + 'what-is-ethereum/'">
            <span class="arrow">→</span
            >{{ translateString('page-home-section-beginners-title') }}
          </router-link>
        </h3>
        <ul>
          <li class="highlight">
            <router-link :to="langPath() + 'what-is-ethereum/'" class="black">
              {{ translateString('page-home-section-beginners-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link :to="langPath() + 'what-is-ethereum/'" class="black">
              {{ translateString('page-home-section-beginners-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link :to="langPath() + 'what-is-ethereum/'" class="black">
              {{ translateString('page-home-section-beginners-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="langPath() + 'use/'">
            <span class="arrow">→</span
            >{{ translateString('page-home-section-use-title') }}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link
              :to="langPath() + 'use/#1-use-an-application-built-on-ethereum'"
              class="black"
            >
              {{ translateString('page-home-section-use-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'use/#2-what-is-eth-and-how-do-i-get-it'"
              class="black"
            >
              {{ translateString('page-home-section-use-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="
                langPath() +
                  'use/#3-what-is-a-wallet-and-which-one-should-i-use'
              "
              class="black"
            >
              {{ translateString('page-home-section-use-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block-nonenglish" v-if="!isEnglish">
        <h3>
          <router-link :to="langPath() + 'learn/'">
            <span class="arrow">→</span
            >{{ translateString('page-home-section-learn-title') }}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link
              :to="langPath() + 'learn/#ethereum-basics'"
              class="black"
            >
              {{ translateString('page-home-section-learn-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'learn/#how-ethereum-works'"
              class="black"
            >
              {{ translateString('page-home-section-learn-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link :to="langPath() + 'learn/#eth-2-0'" class="black">
              {{ translateString('page-home-section-learn-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>

      <div
        v-bind:class="{
          'intro-block': isEnglish,
          'intro-block-nonenglish': !isEnglish
        }"
      >
        <h3>
          <router-link :to="langPath() + 'developers/'">
            <span class="arrow">→</span
            >{{ translateString('page-home-section-developers-title') }}
          </router-link>
        </h3>
        <ul>
          <li v-if="!isEnglish">
            <router-link
              :to="langPath() + 'developers/#getting-started'"
              class="black"
            >
              {{ translateString('page-home-section-developers-item-one') }}
            </router-link>
          </li>
          <li v-if="isEnglish">
            <router-link :to="langPath() + 'build/'" class="black">
              {{ translateString('page-home-section-developers-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'developers/#smart-contract-languages'"
              class="black"
            >
              {{ translateString('page-home-section-developers-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'developers/#developer-tools'"
              class="black"
            >
              {{ translateString('page-home-section-developers-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>

      <div class="intro-block" v-if="isEnglish">
        <h3>
          <router-link :to="langPath() + 'enterprise/'">
            <span class="arrow">→</span
            >{{ translateString('page-home-section-enterprise-title') }}
          </router-link>
        </h3>
        <ul>
          <li>
            <router-link
              :to="langPath() + 'enterprise/#why-enterprise-ethereum'"
              class="black"
            >
              {{ translateString('page-home-section-enterprise-item-one') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'enterprise/#enterprise-features'"
              class="black"
            >
              {{ translateString('page-home-section-enterprise-item-two') }}
            </router-link>
          </li>
          <li>
            <router-link
              :to="langPath() + 'enterprise/#enterprise-developer-community'"
              class="black"
            >
              {{ translateString('page-home-section-enterprise-item-three') }}
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import { translate } from '../theme/utils/translations'

export default {
  computed: {
    // TODO update this to return a contentVersion
    // e.g. English is 1.2, Indonesian is 1.1, all others 1.0
    isEnglish() {
      return this.$lang === 'en-US'
    }
  },
  methods: {
    translateString: function(str) {
      return translate(str, this.$lang)
    },

    langPath: function() {
      return translate('path', this.$lang)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '../theme/styles/config.styl';

  h1
    font-size $fsLarge

  .headline-button
    margin-top 2rem
    font-size $fsRegular

  .header
    color $accentColor

.highlight-small
    background-size 240px !important

  #wrapper.dark-mode
    .header
      color $accentColorDark
</style>
