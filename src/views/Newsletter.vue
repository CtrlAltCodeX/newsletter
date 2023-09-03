<template>
    <div class="main-container">
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
                    ref="btn"
                    title="Click for the error"
                > Subscribe to monthly newsletter</button>
            </div>
        </div>

        <div class="side-image"></div>
    </div>

</template>

<script>
    export default {
        methods: {
            submit() {
                if (! this.$refs['email'].value) {
                    this.$refs['error'].style.color = "red";
                    this.$refs['error'].style.display = "block";

                    this.$refs['email'].style.border = "1px solid red";
                    
                    this.$refs['btn'].style.backgroundImage = "inherit";
                    this.$refs['btn'].style.backgroundColor = "hsl(234, 29%, 20%)";
                }
            }
        }
    };
</script>