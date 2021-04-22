<template>
<div class="container">
    <div class="entradas">
        <input type="number" placeholder="Quantidade em reais" class="entrada" v-model="valorReal">
        <input type="number" placeholder="Cotação do dolar" class="entrada" v-model="valorDolar">

        <div class="botoes">
            <button class="calcular" @click="fazerCalculo()">Calcular</button>
            <button class="limpar" @click="limparCampos()">Limpar</button>  
        </div>
    </div>

    <div class="resultado" v-if="resultado">
        <span>
            Com {{valorReal}} reais é possível comprar {{resultado.toFixed(2)}} dólares a {{valorDolar}} reais cada
        </span>
    </div>
</div>
    
</template>
<script>
export default {
    data(){
        return{
            valorReal: '',
            valorDolar: '',
            resultado: ''
        }
    },
    methods:{
        fazerCalculo(){
            this.resultado = +this.valorReal / +this.valorDolar;
            return this.resultado;  
        },
        limparCampos(){
            this.valorReal = '';
            this.valorDolar = '';
            this.resultado = '';
        }
    }
    
}
</script>
<style scoped>
.container{
    display: flex;
    width: 100%;
    height: 100vh;
    align-items: center;
    justify-content: center;
    background: #363636;
    flex-direction: column;
}
.entradas{
    display: flex;
    flex-direction: column;
    width: 35%;
    transition: .3s ease;
}

input{
    margin-top: .7em;
   padding: 1em;
   background-color: #363636;
   color: white;
   font-weight: 200;
}
input:focus{
   
    box-shadow: 0 0 0 0;
    outline: 0;
                        
}
.botoes{
    margin-top: 1em;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}
.botoes > button{
    padding: .8em .3em;
    margin: .2em;
    border-radius: 25px;
    background-color: #8888cc;
    border: 1px solid #8888cc;
    cursor: pointer;
    color: white;
    flex: 1 1 10em;
}
.resultado{
    padding: .2em;
    margin-top: 1.5em;
    text-align: center;
    font-size: 1.7rem;
    font-weight: 100;
    color: white
}
@media screen and (max-width:530px){
    .entradas{
        width: 70%;
    }

}

</style>