<template>
  <section>
      <headercomponent/>
      <div class="mainContent">
        <div class="col col_4 ccspaceFormHeadCol">
          <p class="para"> Contact: +91 8766774769</p>
<p class="para">email: info@cspace.global</p>
        </div>
        <div class="col col_4 ccspaceFormHeadCol">
            C Space is a creative co-working film incubator with a mission to nurture stories and storytellers to bloom from script to screen.
        </div>
    </div>
    <footercomponent/>
  </section>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  export default {
    data () {
      return {}
    },
    components: {
      headercomponent,
      footercomponent
    }
  }
</script>
<style>
  
</style>
