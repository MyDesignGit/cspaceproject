<template>
    <section class="clearfix formContainer">
        <div class="col col_12 ccspaceFormCol">
            <form class="with100" id="app">

                <div class="input-group">
                   <h1 class="big-heading box bigCapHeading ">what film craft do you
specialize in?</h1>
                    
                </div>
                <div class="boxset carft">
                 <select class="btn btn-yellow" value="" @change="onChange()"   >
                    <option>Producer’s team</option>
                    <option>Unit publicist</option>
                     <option>Insurance</option>
                      <option>Legal</option>
                       <option>Executive producer</option>
                        <option>Line producer</option>
                         <option>Production assistant</option>
                          <option>Production Manager</option>
                           <option>Asst. Prod. Manager</option>
                            <option>Unit Manager</option>
                            <option>Production Coordinator</option>
                        </select>


                  <select class="btn btn-yellow" value="">
                    <option>cinematographer’s team</option>
                    <option> Director of Photography</option>
                     <option>First Assistant Camera</option>
                      <option>Second Assistant Camera</option>
                       <option>Digital Imaging Technician</option>
                        <option>Steadicam operator</option>
                         <option>Motion Control</option>
                          <option>Production Manager</option>
                           <option>Asst. Prod. Manager</option>
                            <option>Unit Manager</option>
                            <option>Production Coordinator</option>
                        </select>

                  <select class="btn btn-yellow" value="">
                    <option>post production team+
                    </option>
                    <option> Director of Photography</option>
                     <option>First Assistant Camera</option>
                      <option>Second Assistant Camera</option>
                       <option>Digital Imaging Technician</option>
                        <option>Steadicam operator</option>
                         <option>Motion Control</option>
                          <option>Production Manager</option>
                           <option>Asst. Prod. Manager</option>
                            <option>Unit Manager</option>
                            <option>Production Coordinator</option>
                        </select>
                        <select class="btn btn-yellow" value="">
                    <option>writer’s team </option>
                    <option>Scriptwriter</option>
                     
                        </select>

                         <select class="btn btn-yellow" value="" @change="onscript()">
                    <option>writer’s team </option>
                    <option>Scriptwriter</option>
                     
                        </select>


                        <select class="btn btn-yellow" value="">
                    <option>writer’s team </option>
                    <option>Scriptwriter</option>
                     
                        </select>

                          <select class="btn btn-yellow" value="">
                    <option>music and sound team</option>
                    <option> Composer</option>
                     <option>Foley Artist</option>
                      <option>Singer</option>
                       <option>Voice Artist</option>
                        <option>Instrumentalist</option>
                         <option>Production Sound Mixer</option>
                          <option>Boom operator</option>
                           <option>Second Assistant Sound</option>
                            <option>Sound Designer</option>
                            <option>Sound Editor</option>
                             <option>Dialogue Editor </option>
                            <option>Score Recorder/Mixer</option>
                        </select>

                           <select class="btn btn-yellow" value="">
                    <option>hair and make up artist team</option>
                    <option>Key Makeup Artist</option>
                     <option>Hair Stylist</option>
                      <option>SFX Makeup</option>
                       <option>Key Hair</option>
                       
                          
                        </select>
                          <select class="btn btn-yellow" value="">
                    <option>director’s team</option>
                    <option>Director</option>
                     <option>Casting director</option>
                      <option>1st AD</option>
                       <option>2nd AD</option>
                       <option>Script supervisor</option>
                       <option>Actors</option>
                       
                          
                        </select>
                        <select class="btn btn-yellow" value="">
                    <option>director’s team</option>
                    <option>Director</option>
                     <option>Casting director</option>
                      <option>1st AD</option>
                       <option>2nd AD</option>
                       <option>Script supervisor</option>
                       <option>Actors</option>
                       
                          
                        </select>

                          <select class="btn btn-yellow" value="">
                    <option>art director’s team</option>
                    <option>Art director</option>
                     <option>Set decorator</option>
                      <option>Set Dresser</option>
                       <option>Assistant Art Director</option>
                        <option>Set Designer</option>
                         <option>Illustrator</option>
                          <option>Graphic Artist</option>
                          
                        </select>
                        </div>
       <!--  <button class="btn btn-yellow"  v-on:click.prevent="hydno()">No</button>  -->
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
                this.$router.push("/createthankyou");
            },
            onChange(value) {

                this.$router.push("/pay");
                    
            },
            onscript(value){
                 this.$router.push("/script");

            }


           
         }
    }
</script>
<style>
  
</style>
