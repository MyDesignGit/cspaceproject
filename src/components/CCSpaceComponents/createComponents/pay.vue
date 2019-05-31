<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <paycomponent/>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import paycomponent from 'components/CCSpaceComponents/createComponents/components/payComponent.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      paycomponent
    }
  }
</script>
<style>  
</style>
