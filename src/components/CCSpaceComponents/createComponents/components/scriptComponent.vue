<template>
<section class="clearfix formContainer">
    <div class="col col_4 ccspaceFormHeadCol">
        <h3 class="subjectCentre bigCapHeading">script
writers</h3>
    </div>
    <div class="col col_4 ccspaceFormCol">
        <form class="fromwidth" id="app">
            <p v-if="errors.length">
                <b>Please correct the following error(s):</b>
                <ul>
                    <li v-for="error in errors">{{ error }}</li>
                </ul>
            </p>
            <!-- Step 0 -->
            <div v-if="step_0">
                <div class="input-group">
                    <label>do you have a full dialogue draft of your script ready?</label>
                    <div class="radioCheckbox-wrap">
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" @click.prevent="createFlow('next', stepcounter)" name="accept-offers" id="yes-button" checked="checked"/>
                        <label class="button-label" for="yes-button">Yes</label>
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" name="accept-offers" id="no-button"/>
                        <label class="button-label" for="no-button">No</label>
                    </div>
                </div>
            </div>
            <!-- Step 1 -->
            <div v-if="step_1">
                 <div class="input-group">
                    <label>have you registered your script with any writer's association? </label>
                    <div class="radioCheckbox-wrap">
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" v-on:click.prevent="payscrpit()" name="accept-offers" id="yes-button" checked="checked"/>
                        <label class="button-label" for="yes-button">Yes</label>
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" name="accept-offers" id="no-button"/>
                        <label class="button-label" for="no-button">No</label>
                    </div>
                </div>
                
            </div>
           
            
            
        </form>
    </div>
</section>
</template>
<script>
export default {
data ()
{
return {
errors: [],
name:'',
contact:'',
email:'',
sproject:'',
investment:'',
meetingdate:'',
type:'connect',


stepcounter:0,
step_0:true,
step_1:false

}
},
methods: {


     checkForm: function (e) {
      if (this.name && this.connect) {
        return true;
      }

      this.errors = [];

      if (!this.name) {
        this.errors.push('Name required.');
      }
      if (!this.contact) {
        this.errors.push('Phone Number required.');
      }

      e.preventDefault();
    },





    payscrpit (elem, e){
    this.$http.post('CSpace/index.php',
    {
    name:this.name,
    contact:this.contact,
    email:this.email,
    sproject:this.sproject,
    investment:this.investment,
    meetingdate:this.meetingdate,
    type:this.types
    
    }).then(function(data){
    console.log(data);
    });
//if you want to send any data into server before redirection then you can do it here
this.$router.push("/payscrpit");
},
createFlow(flowType, stepcount)
    {
        var steps = stepcount;
        if(flowType == "next"){
        steps++;
        this.stepcounter = steps;
        this['step_'+steps] = true;
        this['step_'+(steps-1)] = false;
        if(steps == '6'){
        router.push("createFinal");
        }
        else{
    }
}
else{
steps--;
this.stepcounter = steps;
this['step_'+steps] = true;
this['step_'+(steps+1)] = false;
}
}
}
}
</script>
<style>

</style>