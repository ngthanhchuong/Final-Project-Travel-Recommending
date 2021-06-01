<template>
  <div>
    <TheHeader />
    <Nuxt />

    <TheFooter />
  </div>
</template>

<script>
import TheHeader from '@/components/TheHeader/TheHeader.vue'
import TheFooter from '@/components/TheFooter/TheFooter.vue'
export default {
  components: {
    TheHeader,
    TheFooter,
  },
}
</script>
<style lang=""></style>
