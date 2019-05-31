<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <connectComponent/>

      
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import connectComponent from 'components/CCSpaceComponents/createComponents/components/connectComponent.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      connectComponent
    }
  }
</script>
<style>  
</style>
