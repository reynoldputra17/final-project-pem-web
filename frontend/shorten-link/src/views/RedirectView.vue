<template>
    <div class="bg-[#1F1D2B]">
        <div class="relative z-0 overflow-hidden h-screen ">
            
            <div class="relative z-100 w-screen h-screen flex flex-col justify-center items-center">
                <lottie-player src="../../public/gif/link.json" background="transparent" speed="1" style="width: 200px; height: 200px;" loop autoplay></lottie-player>
                <h1 class="text-[#08A0F7] mt-10"><span class="text-white font-bold">You are being</span> redirected to {{ this.alias }} </h1>
            </div>
            
            <div
            class=" blur-[100px] w-[625px] h-[625px] bg-[#957ADC66] rounded-full -right-44 -bottom-72 -z-10 opacity-60 absolute"
            ></div>
            <div
            class="w-[577px] h-[577px] rounded-full bg-[#00385B] blur-[100px] -top-28 -left-44 -z-10  opacity-60 absolute"
            ></div> 
        </div>
    </div>
</template>

>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            alias: this.$route.params.alias,
            port : 3001
        }
    },  
    async mounted() {
        const res = await axios
        .get(`http://127.0.0.1:${this.port}/api/shorten/in/${this.alias}`)
        .catch((err) => {
          console.log(err);
        });
        setTimeout(() => {
            window.location.assign(`${res.data.data}`);
        }, 3000)
    }
}

</script>