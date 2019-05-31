<template>
    <section class="clearfix formContainer">
       <!--  <div class="col col_4 ccspaceFormHeadCol">
            <h3 class="subjectCentre">Connect</h3>
        </div> -->
<div class="col col_12 ccspaceFormCol">
<form class="form-box" id="app">

  <!-- Step 0 -->
    <!-- <div v-if="step_0">
      <p> C Space believes nuanced screening and rigorous planning on the production aspects to execute great stories with an efficient budget.</p>
    </div> -->
<!-- Step 1 -->

 <div v-if="step_0">
        <div class="input-group">
            <h1 class="big-heading">are you from hyderabfad?</h1>
            <div class="radioCheckbox-wrap ">
                <input class="hidden radio-label floatright rightanimation" type="radio" name="accept-offers" id="no-button"/>
                    <label class="button-label" for="no-button">No</label>
                <input class="hidden radio-label floatright rightanimation" type="radio" name="accept-offers" id="yes-button" checked="checked"/>
                <label class="button-label" for="yes-button">Yes</label>
                    
            </div>
        </div>
    </div>
    
<!-- Step 2 -->
    <div v-if="step_1">
        <div class="input-group">
            <label>email</label>
            <div class="input-field">
                <input type="email" required="email" />
            </div>
        </div>
    </div>
<!-- Step 3 -->
    <div v-if="step_2">
        <div class="input-group">
            <label>name</label>
            <div class="input-field">
                <input v-model="name" type="text" required="name" />
            </div>
        </div>
        <div class="input-group">
            <label>contact No.</label>
            <div class="input-field">
                <input type="text" required="contact" />
            </div>
        </div>
    </div>
<!-- Step 4 -->
    <div v-if="step_3">
        <div class="input-group">
            <label>Scale of investment</label>
            <div class="input-field">
                <input type="email"/>
            </div>
        </div>
    </div>
<!-- Step 5 -->
    <div v-if="step_4">
        <div class="input-group">
            <label>Meeting</label>
                <div class="input-field">
                    <input type="date"/>
                </div>
        </div>
    </div>
    
<!-- Button -->   
    <div class="ccspaceFormBtns clearfix">
        <button class="btn btn-blue" @click.prevent="createFlow('next', stepcounter)">Next</button>
        <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button> 
    </div>

</form>
</div>
    </section>
</template>
<script>
    export default {
        data (
                


            )
         {
            return {
                stepcounter:0,
                step_0:true,
                step_1:false,
                step_2:false,
                step_3:false,
                step_4:false,
                step_5:false
            }
        },
        methods: {
            createFlow(flowType, stepcount){
                var steps = stepcount;
                if(flowType == "next"){
                    steps++;
                    this.stepcounter = steps;
                    this['step_'+steps] = true;
                    this['step_'+(steps-1)] = false;

                    if(steps == '5'){
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
