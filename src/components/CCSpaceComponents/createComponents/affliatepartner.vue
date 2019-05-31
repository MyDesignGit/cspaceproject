<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <affillatepartnerComponents/>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import affillatepartnerComponents from 'components/CCSpaceComponents/createComponents/components/affillatepartnerComponents.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      affillatepartnerComponents
    }
  }
</script>
<style>  
</style>
