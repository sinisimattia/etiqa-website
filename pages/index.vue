<template>
  <div>
    <div>
      <div class="hero is-fullheight">
        <div class="hero-body">
          <div class="container section">
            <div class="columns is-vcentered">
              <div class="column">
                <h1 class="title is-0-desktop is-light is-still">
                  <span>{{ title }}</span>
                </h1>
                <h2 class="subtitle is-4">{{ subtitle }}</h2>
              </div>

              <div class="column">
                <img src="~/assets/img/illustrations/work_together.svg" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <SectionContainer v-if="mainSections" v-bind="mainSections"/>

      <div id="card">
        <SectionContainer
          v-if="cardSections"
          v-bind="cardSections"
          mode="columns"
        />

        <SectionContainer
          v-if="softwareSections"
          v-bind="softwareSections"
          mode="columns"
        />

        <SectionContainer
          v-if="partnerSections"
          v-bind="partnerSections"
          mode="slider"
        />
      </div>
    </div>
  </div>
</template>

<script>
import { identity } from '~/snisni.config.json'
import mainSections from '~/config/home.json'
import cardSections from '~/config/card.json'
import softwareSections  from '~/config/software.json'
import partnerSections from '~/config/partners.json'
import SectionContainer from '@/components/organisms/SectionContainer'

export default {
  components: {
    SectionContainer,
  },
  data() {
    return {
      title: identity.name,
      subtitle: identity.slogan,
      mainSections,
      cardSections,
      softwareSections,
      partnerSections
    }
  },
}
</script>
