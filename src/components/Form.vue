<template>


<div id="form">
    <h1 id="titulo">Formulário</h1>

    <div>
        <input type="text" id="cep"  v-model="cep" placeholder="Digite o cep">
        <button v-on:click="findCep">Calcular</button>
        <label for="cep">DIGITE O CEP</label>
    </div>

    <div id="formu">
        <input type="text" id="cidade" :value=cidade>
        <label for="cidade">Cidade</label>
        <input type="text" id="bairro" :value=bairro>
        <label for="bairro">Bairro</label>
        <input type="text" id="estado" :value=estado>
        <label for="estado">Estado</label>
        <input type="text" id="rua" :value=rua>
        <label for="rua">Rua</label>
    </div>

</div>

    
</template>


<script>
export default {
    el: '#form',
    props:[],
    data(){
        return {
            cidade: "",
            bairro: "",
            rua: "",
            estado: ""
        }
    },
    methods:{

        preencherFormulario(endereco){
            console.log(endereco.logradouro);
            
            this.rua = endereco.logradouro;
            this.bairro = endereco.bairro;
            this.cidade= endereco.localidade;
            this.estado= endereco.uf;

        },


        async findCep() {
          
            let url = "http://viacep.com.br/ws/"+this.cep+"/json/"
            
            
    //fetch(url).then(resp => resp.json()).then(console.log)

            const dados =  await fetch(url)
            const endereco =  await dados.json();

                this.preencherFormulario(endereco);

                }


            },
    
}
</script>




<style scoped>

*{
    color: blanchedalmond;
}


#formu{
    display: grid;
    justify-content: center;
    align-items: center;
   
    margin-top: 30px;
    background-color: rgb(56, 56, 56);
}

label{
    margin: 10px;
}

input{
    width: 250px;
    background-color: rgba(105, 105, 105, 0.651);
    font-size: 1rem;
    color: white;
    border-radius: 5px;
    border: 1px solid black;
}

input::placeholder{
    color: rgb(170, 169, 169);
}
 

 #titulo{
     padding: 20px;
 }


 button{
     color: black;
     width: 100px;
 }
</style>