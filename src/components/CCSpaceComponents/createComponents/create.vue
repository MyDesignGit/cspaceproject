<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <createstepone/>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import createstepone from 'components/CCSpaceComponents/createComponents/components/stepone.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent,
      createstepone
    }
  }
</script>
<style>  
</style>
