<template>
    <vue-instagram token="10474310646.1677ed0.de6fc6dce8d24d0daf7fa16b20bcf5ff" :count="6" :tags="['hyderabad', 'telugumovies','tollywood','cspace']" mediaType="image">
       <template slot="feeds" slot-scope="props">
        <!-- <li class="fancy-list"> {{ props.feed.link }} </li> -->
        <img :src="props.feed.images.low_resolution.url" alt="Image">

    </template>
       <!--  <template slot="error" slot-scope="{ feed }">
            <div> {{ feed.error.error_message }} </div>
        </template> -->
    </vue-instagram>
</template>
<script>
  import headercomponent from 'components/CCSpaceComponents/header.vue'
  import footercomponent from 'components/CCSpaceComponents/footer.vue'
  import Vue from 'vue'
  import VueInstagram from '@silvanite/vue-instagram'
Vue.use(VueInstagram)
 
  export default {
    data () {
      return {}
    }
  }
</script>
<style>  
</style>
