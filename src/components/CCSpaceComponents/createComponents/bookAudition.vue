<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <bookautioncomponent/>

      
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import bookautioncomponent from 'components/CCSpaceComponents/createComponents/components/bookautioncomponent.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      scheduleComponent
    }
  }
</script>
<style>  
</style>
