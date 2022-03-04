
<template>
    <div class="container">
        <img src="../assets/logo.png" alt="logo">
        <h1>My Lotto Generator</h1>
    </div>
    <button @click="generate()">Generate Numbers</button>
    <div class="container">
        <div class="output" v-for="digit in randomDigits" :key="digit"> 
            {{ digit }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        generate(){
            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
        }
    }
}
</script>

<style scoped>
.container{
    display: flex;
    align-items: center;
    justify-content: center;
}
img{
    height: 60px;
    padding: 5px;
}

button{
    margin-left: 587px;
    margin-bottom: 7px;
    padding: 10px;
    background: #eee;
    border: solid 1px #ddd;
    font-size: 18px;
    color: #555;
    cursor: pointer;
    outline: none;
}
button:hover{
    background: #999;
    color: #fff;
}

.output {
    padding: 7px;
    font-size: 18pt;
}

</style>