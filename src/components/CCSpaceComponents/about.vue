<template>
  <section>
      <headercomponent/>
      <div class="mainContent">
       <div class="box">
        <p>
           C Space is a creative co-working film incubator with a mission to nurture stories and storytellers to bloom from script to screen. 
        </p>
        <p>
            C Space believes in being accessible to passionate filmmakers, in treating creators with dignity, and in nurturing their path to screen.
        </p>
        </div>
        <h3 class="rightHeading">about us </h3>
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

