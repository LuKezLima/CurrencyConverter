<template>

<div class="conversor">
    <h2>{{moedaA}} para {{moedaB}}</h2>
    <div id="inputs">
         <input type="text" id="text" v-model="moedaA_value" :placeholder=moedaA>
    <input id="button" type="button" v-on:click="converter" value="Converter">
    </div>
    <h2 id="result">{{moedaB_value}}</h2>


</div>
    
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data(){
        return {
            moedaA_value: "",
            moedaB_value: 0

        }
    },

    methods: {
        converter(){
            let de_Para = this.moedaA + "_" + this.moedaB;
            let url = "https://free.currconv.com/api/v7/convert?q="+ de_Para +"&compact=ultra&apiKey=06e9132540455b5f3eee"


            fetch(url)
            .then(response => {return response.json()})
            .then(json => {
                let cotacao = json[de_Para];
                console.log(cotacao);
              console.log(json);
                
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
            })

            
        },
    },


}
</script>


<style scoped>


.conversor{
    width: 30%;
    height: 60%;
    padding: 30px;
    border: black 1px solid;
    border-radius: 5px;
     background: linear-gradient(to right, #76b852, #8dc26f);
}


h2{
    color: white;
}

#text{
    height: 30px;
    border-radius: 3px;
    border: none;
}

#inputs{
    margin-top: 10px;
}

#button{
    width: 20%;
    text-align: center;
    padding: 4px;
    height: 30px;
    margin-left: 8px;
    border-radius: 3px;
    background-color: #2c3e50dc; 
    color: white;
    border: none;
    cursor: pointer;
}


#result{
    margin-top: 10px;
}

</style>
