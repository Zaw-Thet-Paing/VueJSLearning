<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click here {{ delay }}
  </div>
  
</template>

<script>
export default {
    props: [
        'delay'
    ],
    data(){
        return {
            showBlock: false,
            score: 0,
            timer: null
        }
    },
    methods:{
        startTimer(){
            this.timer = setInterval(()=>{
                this.score += 50
            }, 50)
        },
        stopTimer(){
            clearInterval(this.timer)
            // console.log(this.score)
            this.$emit("endGame", this.score)
        }
    },
    mounted(){
         setTimeout(()=>{
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    }
}
</script>

<style scoped>
    .block{
        background-color: aqua;
        width: 400px;
        height: 300px;
        margin: 20px auto;
        padding-top: 30px;
    }
</style>