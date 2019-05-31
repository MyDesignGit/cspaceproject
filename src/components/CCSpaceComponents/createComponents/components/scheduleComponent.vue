<template>
 <section class="clearfix formContainer">
  <div class="col col_5 ccspaceFormHeadCol">
    <div class="rightalign bigCapHeading">
        <button class="schedulebtn rightalign line" v-on:click.prevent="fulltime()">full-time</br>membership</button>
    </div>
 </div>
 <div class="col col_5 ccspaceFormCol rightanimation2">
    <button class="schedulebtn leftalign " v-on:click.prevent="parttime()">weekend</br>membership</button>
</div>


    </section>
</template>
<script>
export default {
    data ()
    {
        return {} 
    },
     methods: {
            fulltime(elem, e)
            {
                this.$router.push("/fulltimemembership");
            },
            parttime(elem, e)
            {
                this.$router.push("/weekendmembership");
            }
           
         }               
            
         }
  
</script>
