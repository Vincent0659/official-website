<template>
  <div id="home">
    <section-top />
    <section-new />
    <!-- <section-video /> -->
    <section-technology />
    <section-products />
    <section-framework />
    <section-customer />
    <section-global />
    <section-steps />
    <section-roadmap />
    <section-partners />
    <section-future ref="scrollFuture" />
  </div>
</template>

<script>
import SectionTop from '@/components/IndexSections/SectionTop.vue'
import SectionNew from '@/components/IndexSections/SectionNew.vue'
import SectionVideo from '@/components/IndexSections/SectionVideo.vue'
import SectionTechnology from '@/components/IndexSections/SectionTechnology.vue'
import SectionProducts from '@/components/IndexSections/SectionProducts.vue'
import SectionFramework from '@/components/IndexSections/SectionFramework.vue'
import SectionCustomer from '@/components/IndexSections/SectionCustomer.vue'
import SectionGlobal from '@/components/IndexSections/SectionGlobal.vue'
import SectionSteps from '@/components/IndexSections/SectionSteps.vue'
import SectionRoadmap from '@/components/IndexSections/SectionRoadmap.vue'
import SectionPartners from '@/components/IndexSections/SectionPartners.vue'
import SectionFuture from '@/components/IndexSections/SectionFuture.vue'
export default {
  components: {
    SectionTop,
    SectionNew,
    SectionVideo,
    SectionTechnology,
    SectionProducts,
    SectionFramework,
    SectionCustomer,
    SectionGlobal,
    SectionSteps,
    SectionRoadmap,
    SectionPartners,
    SectionFuture,
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start()
      setTimeout(() => this.$nuxt.$loading.finish(), 1000)
    })
  },
  methods: {},
}
</script>
