<template>
    <div class="container">
        <img src="../assets/pcso-logo.png" alt="">
        <h1>My Lotto Generator</h1>
    </div>
    <div class="container">
        <h4 v-for="numberArray in numbersArray" :key="numberArray">
            {{ numberArray }}
        </h4>
    </div>
    <div class="container">
        <button @click="generate()">Generate Number</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            numbersArray : []
        }
    },
    methods: {
        generate(){
            while(this.numbersArray.length < 6){
                let random = Math.floor(Math.random() * 41)+ 1;
                if(!this.numbersArray.includes(random)){
                    this.numbersArray.push(random);
                }
            }
        }
    }
}
</script>

<style scope>

img{
    height: 100px;
}

.container{
    display: flex;
    align-items: center;
    justify-content: center;
}

button{
    padding: 10px;
}
h4{
   padding: 10px;
}

</style>