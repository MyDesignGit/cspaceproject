<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <influencersComponents/>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import influencersComponents from 'components/CCSpaceComponents/createComponents/components/influencersComponents.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      influencersComponents
    }
  }
</script>
<style>  
</style>
