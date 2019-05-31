<template>
<section class="clearfix formContainer">
    <div class="col col_4 ccspaceFormHeadCol">
        <h3 class="subjectCentre bigCapHeading">workshop</br>
partners</h3>
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
                <p>C Space is looking for reputed organisations which conduct workshops relevant to filmmaking to build an annual weekday calendar of weekday and weekend workshops. How can you help?
</p>
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
                    <button class="btn btn-blue" v-bind="{disabled:!(name&&contact)}" @click.prevent="createFlow('next', stepcounter)">Next</button>
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
                    <button  class="btn btn-blue" v-bind="{disabled:!(email)}" @click.prevent="createFlow('next', stepcounter)">next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">back</button>
                </div>
            </div>
            <!-- Step 3 -->
            <div v-if="step_3">
                <div class="input-group">
              
                   <label>what kind of workshops can you conduct?</label>
                       <textarea rows="6" cols="80" class="bordercolor"></textarea>
                     <div class="ccspaceFormBtns clearfix">
                    <button  class="btn btn-blue" v-bind="{disabled:!(email)}" @click.prevent="createFlow('next', stepcounter)">next</button>
                    <button class="btn btn-yellow" @click="createFlow('back', stepcounter)">back</button>
                </div>
                </div>
            </div>
            <!-- Step 4 -->
            <div v-if="step_4">
                <div class="input-group">
                   
                    <div  class="input-field">
                        <label>how many workshops can you</br>
conduct in a year?</label>
                       <input v-model="conductYear" type="number" required="email" />
                        
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

</style>