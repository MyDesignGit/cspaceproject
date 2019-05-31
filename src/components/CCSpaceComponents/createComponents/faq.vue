<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <div class="box">
        <input class="m-auto" type="text" v-model="search" placeholder="search faq">
        <div v-for="blog in filteredBlogs" class="newcol col_45 padding20" >
          <h5 class="text_align_left">{{blog.title}}</h5>
          <p class="para text_align_left">{{blog.body}}</p>
        </div>
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
      return {
        blogs:[],
        search:''
      }
    },
    methods:{

    },
    created(){
      this.$http.get('http://localhost:8080/static/json/faq.json').then(function(data){
          this.blogs = data.body.slice(0,17);
        console.log(data);
      })
    },
    computed:{
      filteredBlogs:function(){
        return this.blogs.filter((blog)=>{
          return blog.title.match(this.search);
        });
      }
    },



    components: {
      headercomponent,
      footercomponent,
      
    }
  }
</script>
<style>  
</style>
