<template>
    <div class="main-container thank-container">
        <div class="container-one">
            <img src="/icon-success.svg" style="margin-bottom:30px;">
            
            <h1 style="line-height:55px;margin-bottom: 20px;">Thanks for <br> subscribing!</h1>
            
            <p style="margin-bottom:20px;">A confirmation email has been sent to <br> <b>as@gmail.com</b> Please open it and click <br> the button inside the to confirm your subscription</p>

            <div>
                <button class="sub-btn" ref="btn" @click="dismissMsg()">Dismiss message</button>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        methods: {
            dismissMsg() {
                this.$refs['btn'].style.backgroundImage = "inherit";
                this.$refs['btn'].style.backgroundColor = "hsl(234, 29%, 20%)";
            }
        }
    }
</script>