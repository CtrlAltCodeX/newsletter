<template>
    <div class="main-container" v-if="active">
        <div class="container-one">
            <h1>Stay updated!</h1>
            <p>Join 60,000+ product managers recieving monthly <br> updates on:</p>

            <div class="key-point">
                <p class="d-flex mb-5"><img src="/icon-list.svg" width="18" height=20 class="mr-5">Product Discovery and building what matter</p>
                <p class="d-flex mb-5"><img src="/icon-list.svg" width="18" height=20 class="mr-5">Measuring to ensure the update are a success</p>
                <p class="d-flex mb-5"><img src="/icon-list.svg" width="18" height=20 class="mr-5">and much more! </p>
            </div>

            <div>
                <label>
                    <div class="d-flex justify-content-between">
                        <span>Email address</span>
                        <span ref="error" style="display:none">Valid email required</span>
                    </div>
                    <input type="text" ref="email">
                </label>
                <br>
                <br>

                <button 
                    class="sub-btn"
                    @click="submit()"
                    @mouseover="hoverEffect()"
                    ref="btn"
                    title="Click for the error"
                > Subscribe to monthly newsletter</button>
            </div>
        </div>

        <div class="side-image"></div>
    </div>


    <div class="main-container thank-container" v-else>
        <div class="container-one">
            <img src="/icon-success.svg" style="margin-bottom:30px;">
            
            <h1 style="line-height:55px;margin-bottom: 20px;">Thanks for <br> subscribing!</h1>
            
            <p style="margin-bottom:20px;">A confirmation email has been sent to <br> <b>as@gmail.com</b> Please open it and click <br> the button inside the to confirm your subscription</p>

            <div>
                <button 
                    class="sub-btn" 
                    ref="btn" 
                    @click="dismissMsg()"
                    @mouseover="hoverEffect()">Dismiss message</button>
            </div>
        </div>
    </div>

</template>

<script>
    export default {

        data() {
            return {
                active: true
          }
        },

        methods: {
            submit() {
                var email_pattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;

                const validEmail = email_pattern.test(this.$refs['email'].value);

                if (! this.$refs['email'].value || ! validEmail) {
                    this.$refs['error'].style.color = "red";
                    this.$refs['error'].style.display = "block";

                    this.$refs['email'].style.border = "1px solid red";
                } else {
                    this.active = false;
                }
            },
            
            hoverEffect() {
                this.$refs['btn'].style.backgroundImage = "inherit";
                this.$refs['btn'].style.backgroundColor = "hsl(234, 29%, 20%)";
            },

            dismissMsg() {
                this.active = true;
                this.$refs['btn'].style.backgroundImage = "inherit";
                this.$refs['btn'].style.backgroundColor = "hsl(234, 29%, 20%)";
            }
        }
    };
</script>