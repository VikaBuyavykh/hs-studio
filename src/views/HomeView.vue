<script setup>
import AppCover from '@/components/AppCover.vue'
import AppAdvantages from '@/components/AppAdvantages.vue'
import AppProjects from '@/components/AppProjects.vue'
import AppStages from '@/components/AppStages.vue'
import AppPricing from '@/components/AppPricing.vue'
import AppTeam from '@/components/AppTeam.vue'
import AppForm from '@/components/AppForm.vue'
</script>

<template>
  <AppCover />
  <AppAdvantages />
  <AppProjects />
  <AppStages />
  <AppPricing />
  <AppTeam />
  <AppForm />
</template>

<style lang="scss" scoped>
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;
</style>
