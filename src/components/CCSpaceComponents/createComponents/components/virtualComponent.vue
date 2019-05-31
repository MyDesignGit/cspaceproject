<template>
    <section class="clearfix formContainer">
        <div class="col col_4 ccspaceFormHeadCol">
            <h3 class="text_align_left subjectCentre bigCapHeading ">virtual</br>
membership</h3>
        </div>
<div class="col col_4 ccspaceFormCol">
<form class="fromwidth" id="app">

  <!-- Step 0 -->
    <div v-if="step_0">
      <p> C Space is a network of artists from across the globe who can collaborate and co-create great films irrespective of their geographical constraints.</p>
      <!-- Button -->   
    <div class="ccspaceFormBtns clearfix">
        <button class="btn btn-blue" @click.prevent="createFlow('next', stepcounter)">Next</button>
        <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button> 
    </div>
    </div>

<!-- Step 1 -->
    <div v-if="step_1">
        <div class="input-group">
            <label>name</label>
            <div class="input-field">
                <input v-model="name" type="text" />
            </div>
        </div>
        <div class="input-group">
            <label>contact no.</label>
            <div class="input-field">
                <input v-model="contact"  type="number" />
            </div>
        </div>
        <!-- Button -->   
    <div class="ccspaceFormBtns clearfix">
        <button class="btn btn-blue" @click.prevent="createFlow('next', stepcounter)">Next</button>
        <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button> 
    </div>
    </div>
<!-- Step 2 -->
    <div v-if="step_2">
        <div class="input-group">
            <label>email</label>
            <div class="input-field">
                <input v-model="email" type="email" required="email" />
            </div>
        </div>
        <!-- Button -->   
   <div class="ccspaceFormBtns clearfix">
                    
                    <button class="btn btn-blue"  @click="createFlow('next', stepcounter)">Next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
                </div>
    </div>
<!-- Step 3 -->
<div v-if="step_3">
        <div class="input-group">
            <label>what workshops are you interested in?</label>
            <!-- <div class="input-field">
                <input v-model="email" type="email" required="email" />
            </div> -->
        </div>
        <!-- Button -->   
   <div class="ccspaceFormBtns clearfix">
                    
                    <button class="btn btn-selecion" @click="createFlow('next', stepcounter)">Scrpit</button>
                     <button class="btn btn-selecion" @click="createFlow('next', stepcounter)" >Production Design</button>
                      <button class="btn btn-selecion" @click="createFlow('next', stepcounter)">Cinatography</button>
                       <button class="btn btn-selecion" @click="createFlow('next', stepcounter)">Music &amp; Sound</button>
                        <button class="btn btn-selecion" @click="createFlow('next', stepcounter)">Edit</button>
                        <button class="btn btn-selecion" v-on:click.prevent="carft()">Acting</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">back</button>
                </div>
    </div>

     <!-- Step 4 -->
            <div v-if="step_4">
                <div class="input-group">
                    <label>can you attend weekday workshops?</label>
                    <div class="radioCheckbox-wrap">
                        <input v-model="weekday" value="yes" class="hidden radio-label" type="radio" @click.prevent="createFlow('next', stepcounter)" name="accept-offers" id="yes-button" checked="checked"/>
                        <label class="button-label" for="yes-button">Yes</label>
                        <input v-model="weekday" value="yes" class="hidden radio-label" type="radio" name="accept-offers" id="no-button"/>
                        <label class="button-label" for="no-button">No</label>
                    </div>
                </div>
            </div>
             <!-- Step 5 -->
            <div v-if="step_5">
                <div class="input-group">
                    <label>are you interested in 
volunteering for C Space events?</label>
                    <div class="radioCheckbox-wrap">
                        <input v-model="weekday" value="yes" class="hidden radio-label" type="radio" v-on:click.prevent="post()" name="accept-offers" id="yes-button" checked="checked"/>
                        <label class="button-label" for="yes-button">Yes</label>
                        <input v-model="weekday" v-on:click.prevent="post()" value="yes" class="hidden radio-label" type="radio" name="accept-offers" id="no-button"/>
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
       
            name:'',
            contact:'',
            email:'',
           type:'connect',
           
      
 stepcounter:0,
            step_0:true,
            step_1:false,
            step_2:false,
            step_3:false,
            step_4:false,
            step_5:false,
          

    }
                },


        methods: {

                post(elem, e){

            this.$http.post('http://207.38.84.105/CSpace/index.php',{
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

        this.$router.push("/connectthankyou");
      },
 carft(elem, e){

this.$router.push("/specialize");

 },


            createFlow(flowType, stepcount){
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
