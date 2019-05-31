<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <fulltimeComponent/>
  
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import fulltimeComponent from 'components/CCSpaceComponents/createComponents/components/fulltimeComponent.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      fulltimeComponent
    }
  }
</script>
<style>  
</style>
