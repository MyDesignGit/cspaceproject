<template>
<section class="clearfix formContainer">
    <div class="col col_4 ccspaceFormHeadCol">
        <h3 class="subjectCentre bigCapHeading">Create</h3>
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
            <div v-if="step_0" class="rightanimation">
                <p> C Space believes nuanced screening and rigorous planning on the production aspects to execute great stories with an efficient budget.</p>
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
                    <div class="input-field">
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
                    <label>Interested in looking at our slate of projects?</label>
                    <div class="radioCheckbox-wrap">
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" @click.prevent="createFlow('next', stepcounter)" name="accept-offers" id="yes-button" checked="checked"/>
                        <label class="button-label" for="yes-button">Yes</label>
                        <input v-model="sproject" value="yes" class="hidden radio-label" type="radio" name="accept-offers" id="no-button"/>
                        <label class="button-label" for="no-button">No</label>
                    </div>
                </div>
            </div>
            <!-- Step 4 -->
            <div v-if="step_4" class="rightanimation">
                <div class="input-group">
                    <label>Scale of investment:{{investment*500000}}</label>
                    <div  class="input-field">
                        <div class="slidecontainer">
                            <!-- <input  v-model="investment" type="range" min="500000" max="5000000" value="50" class="slider" id="myRange"> -->
                            <VueSlideBar
                                v-model="investment"
                                :min="1"
                                :max="100"
                                :processStyle="slider.processStyle"
                                :lineHeight="slider.lineHeight"
                                :tooltipStyles="{ backgroundColor: 'red', borderColor: 'red' }">
                                </VueSlideBar>
                        </div>
                        
                    </div>
                </div>
                <!-- Button -->
                <div class="ccspaceFormBtns clearfix">
                    <button class="btn btn-blue" @click.prevent="createFlow('next', stepcounter)">Next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
                </div>
            </div>
            <!-- Step 5 -->
            <div v-if="step_5" class="rightanimation">
                <div class="input-group">
                    <label>Meeting</label>
                    <div class="input-field">
                        <input v-model="meetingdate" type="date"/>
                    </div>
                </div>
                <!-- Button -->
                <div class="ccspaceFormBtns clearfix">
                    
                    <button class="btn btn-blue"  v-on:click.prevent="post()">submit</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">Back</button>
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
            type:'connect',
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
            step_5:false,
            step_6:false
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
                this.$router.push("/createthankyou");
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

</style>