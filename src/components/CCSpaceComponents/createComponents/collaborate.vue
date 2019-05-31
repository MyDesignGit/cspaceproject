<template>
  <section>
    <headercomponent/>
    <div class="mainContent">
      <div class="btnbox">
      <div class="btnc">
        <button  v-on:click.prevent="inf()" >influencers</button>
      </div>
      <div class="btnc">
        <button v-on:click.prevent="wp()" >workshop partners</button>
      </div>
       <div class="btnc">
        <button v-on:click.prevent="apt()" >actor + producer team</button>
      </div>
       <div class="btnc">
        <button v-on:click.prevent="af()">affiliate partners</button>
      </div>
      </div>
    <h3 class="rightHeading">collaborate</h3>
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
      footercomponent,
      
    },
    methods:{
       inf(elem, e){
          
                //if you want to send any data into server before redirection then you can do it here
                this.$router.push("/influencers");
        },
        wp(elem, e){
          
                //if you want to send any data into server before redirection then you can do it here
                this.$router.push("/workshop");
        },
        apt(elem, e){
          
                //if you want to send any data into server before redirection then you can do it here
                this.$router.push("/apteam");
        },
        af(elem, e){
          
                //if you want to send any data into server before redirection then you can do it here
                this.$router.push("/affillatepartner");
        },
    }
  }
</script>
<style>  

.btnc{
  background-color: #F9B131;
  height: 20px;
  width: 50%;
  margin:10px auto;
  padding: 20px;
  font-size: 20px;
  line-height: 16px;
  border-radius: 30px;
  cursor:pointer;
  margin-left: 0px;
  transition: 0.3s;
  float: right;

}

.btnc button{
  font-size: 20px;
  color: #0B4D8A;
  width: 100%;
   cursor:pointer;
   margin-left: -150px;
   transition: ease 0.5s;

 
}

.btnc:hover button {
  margin-left:20px;

  
}
</style>
