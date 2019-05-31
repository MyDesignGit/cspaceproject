<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <aptemComponents/>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import aptemComponents from 'components/CCSpaceComponents/createComponents/components/aptemComponents.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      aptemComponents
    }
  }
</script>
<style>  
</style>
