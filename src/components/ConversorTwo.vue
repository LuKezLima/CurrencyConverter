<template>

<div class="conversorTwo">
    <div>
        <input type="text" v-model="moedaA_value" placeholder="Digite o valor em Real">
        <button v-on:click="converter">Converter</button>
    </div>

    <div>
        <h2>{{moedaB}}</h2>
        <h3>{{moedaB_value}}</h3>
    </div>
      <div>
        <h2>{{moedaC}}</h2>
        <h3>{{moedaC_value}}</h3>
    </div>

</div>
    
</template>

<script>
export default {
    name: "ConversorTwo",
    props: ["moedaB", "moedaC"],
    data(){
        return {
            moedaB_value:  0,
            moedaC_value: 0

        }
    },

    methods: {
        converter(){
            console.log(this.$data);
            
            
            for(let item in this.$props){
                
                console.log(item);
                
            let de_Para = "BRL" + "_" + this.$props[item];
            let url = "https://free.currconv.com/api/v7/convert?q="+ de_Para +"&compact=ultra&apiKey=06e9132540455b5f3eee"



                for(let value in this.$data){
                 fetch(url)
                .then(response => {return response.json()})
                .then(json => {
                 let cotacao = json[de_Para];

                
               
                this.$data[value] = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
                
    
                
            }
            
            )
            }
                

            }
            
        },
    },


}
</script>


<style scoped>


</style>
