<template>
<section class="clearfix formContainer">
    <div class="col col_4 ccspaceFormHeadCol">
        <h3 class="subjectCentre bigCapHeading">Pay</h3>
    </div>
    <div class="col col_4 ccspaceFormCol">
     <div class="fromwidth rightanimation"><h1 class="payportal ">Pay Portal</h1>

      
        <button class="btn btn-blue" v-on:click.prevent="payoption()" id="rzp-button1">Next</button>
        </div>
    </div>
</section>
</template>

<script src="https://checkout.razorpay.com/v1/checkout.js"></script>
 
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
step_1:false,
step_2:false,
step_3:false,
step_4:false,
step_5:false,
step_6:false
}
},
methods: {




    //  checkForm: function (e) {
    //   if (this.name && this.connect) {
    //     return true;
    //   }

    //   this.errors = [];

    //   if (!this.name) {
    //     this.errors.push('Name required.');
    //   }
    //   if (!this.contact) {
    //     this.errors.push('Phone Number required.');
    //   }

    //   e.preventDefault();
    // },


payoption(elem,e){

//     var options = {
//     "key": "rzp_test_EW4KZOHU49tAMN",
//     "amount": "2000", // 2000 paise = INR 20
//     "name": "Merchant Name",
//     "description": "Purchase Description",
//     "image": "",
//     "handler": function (response){
//         alert(response.razorpay_payment_id);
//     },
//     "prefill": {
//         "name": "Gaurav Kumar",
//         "email": "test@test.com"
//     },
//     "notes": {
//         "address": "Hello World"
//     },
//     "theme": {
//         "color": "#F37254"
//     }
// };
// var rzp1 = new Razorpay(options);

// document.getElementById('rzp-button1').onclick = function(e){
//     rzp1.open();
//     e.preventDefault();
// }
this.$router.push("/createthankyou");
},


    // post(elem, e){
    // this.$http.post('CSpace/index.php',
    // {
    // name:this.name,
    // contact:this.contact,
    // email:this.email,
    // sproject:this.sproject,
    // investment:this.investment,
    // meetingdate:this.meetingdate,
    // type:this.types
    
    // }).then(function(data){
    // console.log(data);
    // });
//if you want to send any data into server before redirection then you can do it here
// this.$router.push("/createthankyou");
// },
// createFlow(flowType, stepcount)
    // {
        // var steps = stepcount;
        // if(flowType == "next"){
        // steps++;
        // this.stepcounter = steps;
        // this['step_'+steps] = true;
        // this['step_'+(steps-1)] = false;
        // // if(steps == '6'){
        // router.push("createFinal");
        // }
    //     else{
    // }
// }
// else{
// steps--;
// this.stepcounter = steps;
// this['step_'+steps] = true;
// this['step_'+(steps+1)] = false;
// }
// }
}
}
</script>
<style>

</style>