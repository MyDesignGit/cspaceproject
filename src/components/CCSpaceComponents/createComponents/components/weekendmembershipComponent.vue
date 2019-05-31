<template>
    <section class="clearfix formContainer">
        <div class="col col_4 ccspaceFormHeadCol">
            <h3 class="text_align_left subjectCentre bigCapHeading">Weekend</br>
membership</h3>
        </div>
<div class="col col_4 ccspaceFormCol">
<form class="fromwidth" id="app">

  <!-- Step 0 -->
    <div v-if="step_0">
      <p> C Space is on a mission to nurture stories and storytellers (of all filmmaking crafts) to bloom from script to screen. </p>
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
        <button class="btn btn-blue" v-bind="{disabled:!(name&&contact)}"  @click.prevent="createFlow('next', stepcounter)">Next</button>
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
                    
                    <button class="btn btn-blue" v-bind="{disabled:!(email)}" v-on:click.prevent="carft()">Next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
                </div>
    </div>
<!-- Step 3 -->
    
    
    


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
           membership:'Weekend',
           
      
 stepcounter:0,
            step_0:true,
            step_1:false,
            step_2:false,
            step_3:false,
          

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

        this.$router.push("/createthankyou");
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
