<template>
    <section class="clearfix formContainer">
        <div class="col col_12 ccspaceFormCol">
            <form class="form-box" id="app">
                <div class="input-group">
                    <h1 class="big-heading bigCapHeading">are you from hyderabad?</h1>
                </div>
               
        <button class="btn btn-yellow floatright bigbtn rightanimation"  v-on:click.prevent="hydno()">No</button> 
          <button  class="btn btn-yellow floatright bigbtn rightanimation2" v-on:click.prevent="hydyes()">Yes</button>
            </form>

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
            hydyes(elem, e)
            {
                this.$router.push("/schedule");
            },
            hydno(elem, e)
            {
                this.$router.push("/virtualmembership");
            }
           
         }
    }
</script>
<style>
  
</style>
