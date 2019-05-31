<template>
<section class="clearfix formContainer">
    <div class="col col_4 ccspaceFormHeadCol">
        <h3 class="subjectCentre bigCapHeading">actor +</br>producer</br>team</h3>
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
                <p>C Space aims to build a network of key influencers who can help us build a niche customer base engaged with our vision. How can you help?</p>
                <!-- Button -->
                <div class="ccspaceFormBtns clearfix">
                    <button class="btn btn-blue" @click.prevent="createFlow('next', stepcounter)">Next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
                </div>
            </div>
            <!-- Step 1 -->
            <div v-if="step_1" class="rightanimation">
                <div class="input-group">
                    <label>name</label>
                    <div class="input-field">
                        <input v-model="name" type="text" />
                    </div>
                </div>
                <div class="input-group">
                    <label>contact no.</label>
                    <div class="input-field" class="rightanimation">
                        <input v-model="contact"  type="number" />
                    </div>
                </div>
                <!-- Button -->
                <div class="ccspaceFormBtns clearfix">
                    <button class="btn btn-blue" v-bind="{disabled:!(name&&contact)}" @click.prevent="createFlow('next', stepcounter)">Next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
                </div>
            </div>
            <!-- Step 2 -->
            <div v-if="step_2" class="rightanimation">
                <div class="input-group">
                    <label>email</label>
                    <div class="input-field">
                        <input v-model="email" type="email" required="email" />
                    </div>
                </div>
                <!-- Button -->
                <div class="ccspaceFormBtns clearfix">
                    <button  class="btn btn-blue" v-bind="{disabled:!(email)}" @click.prevent="createFlow('next', stepcounter)">next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">back</button>
                </div>
            </div>
            <!-- Step 3 -->
            <div v-if="step_3" class="rightanimation">
                <div class="input-group">
                    <label>when do you want to schedule</br>
a meeting?</label>
                    <div class="radioCheckbox-wrap">
                        <input class="mt-20" v-model="slinks1" type="date" required="email" />
                        
                    </div>
                     <div class="ccspaceFormBtns clearfix">
                   <button class="btn btn-blue"  v-on:click.prevent="post()">submit</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">back</button>
                </div>
                </div>
            </div>
            
           
            
            
        </form>
    </div>
</section>
</template>
<script>
import VueSlideBar from 'vue-slide-bar'
export default {
    data ()
    {
        return {
            errors: [],
            name:'',
            contact:'',
            email:'',
            sproject:'',
            //investment:'',
            meetingdate:'',
            type:'collaborate',
            investment: 10,
            slider: {
                lineHeight: 10,
                processStyle: {
                backgroundColor: 'red'
                }
            },
            stepcounter:0,
            step_0:true,
            step_1:false,
            step_2:false,
            step_3:false,
            step_4:false,
            step_5:false
           
        }
    },
    components: {
        VueSlideBar
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
        post(elem, e){
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
                this.$router.push("/collaboratethankyou");
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
                else{}
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

.bordercolor{
    border: 1px solid #F9B131;
    border-radius: 10px;
}
.subjectCentre{
    text-align: left;
}
</style>