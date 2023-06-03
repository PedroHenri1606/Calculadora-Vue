<template>
    <div class="d-flex justify-content-center">
    
      <table class="table w-25">
        <tbody>
        <tr> 
        <td class= "topoTabela" colspan="4">{{ output || 0 }}</td> 
      </tr>
      <tr>
        <td @click="limpar()" class="botaoCalculoSuperior">C</td>
        <td @click="positivoOuNegativo()" class="botaoCalculoSuperior">+/-</td>
        <td   class="botaoCalculoSuperior">%</td>
        <td class= "table-warning botaoCalculo" >÷</td>
      </tr>
      <tr>
        <td @click="somaNumero(7)" class="botao">7</td>
        <td @click="somaNumero(8)" class="botao">8</td>
        <td @click="somaNumero(9)" class="botao">9</td>
        <td class= "table-warning botaoCalculo" @click="efetuaCalculo('multiplicacao')">X</td>
      </tr>
      <tr>
        <td @click="somaNumero(4)" class="botao">4</td>
        <td @click="somaNumero(5)" class="botao">5</td>
        <td @click="somaNumero(6)" class="botao">6</td>
        <td class= "table-warning botaoCalculo" @click="efetuaCalculo('subtrarir')">-</td>
      </tr>
      <tr>
        <td @click="somaNumero(1)" class="botao">1</td>
        <td @click="somaNumero(2)" class="botao">2</td>
        <td @click="somaNumero(3)" class="botao">3</td>
        <td class= "table-warning botaoCalculo" @click="efetuaCalculo('adicao')">+</td>
      </tr>
      <tr>
        <td @click="somaNumero(0)" colspan="2" class="botao">0</td>
        <td @click="somaNumero('.')" class="botao">.</td>
        <td @click="chamaCalculo()" class="botaoCalculo">=</td>
      </tr>

        </tbody>
      </table>
    
    </div>
</template>


<script>
export default {
  name: 'CalculadoraTeste',
  props: {
    msg: String
  },
  data(){
    return{
      output:'',
      valorAntigo: null,
      operadorClicado: false,
    }
    },
    methods:{

      somaNumero(x){
        if(this.operadorClicado){
          this.output = '';
          this.operadorClicado=false;
        }
        this.output=`${this.output}${x}`
      },

      limpar(){
        this.output = ''  ;
      },

      positivoOuNegativo(){
        this.output = this.output[0] === '-' ? this.output.slice(1):`-${this.output}`;
      },

      efetuaCalculo(calculo){
        
        if(calculo === 'adicao'){
          this.calculo =(a,b) =>{
            return parseFloat(a)+parseFloat(b);
          }
        } else if(calculo === 'subtrair'){
          this.calculo =(a,b) =>{
            return parseFloat(a)-parseFloat(b);
          }
        }
        if(calculo === 'dividir'){
          this.calculo=(a,b) =>{
            return parseFloat(a)/parseFloat(b);
          }
        }
        if(calculo === 'multiplicacao'){
          this.calculo=(a,b)=>{
            return parseFloat(a)*parseFloat(b);
          }
        }
        
        this.valorAntigo = this.output;
        this.operadorClicado=true;
        this.output = '';
      },

      chamaCalculo(){
        this.output = `${this.calculo(this.valorAntigo, this.output)}`;
        this.valorAntigo = null;
      }

    }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

table{
  background-color: black;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.topoTabela{
  font-size: 50px;
  color: white;
  background-color: black;
  border-color: black;
  border-radius: 500px;
  text-align: right;
  transform: scale(0.9);
}

.botao{
  color: white;
  background-color: rgba(37, 37, 37, 0.829);
  font-size: 50px;
  border-color: black;
  border-radius: 100px;
  height: 90px;
  width: 80px;
  transform: scale(0.9);
  transition: 1s;
 
}

.botao:hover{
  transition: 1s;
  font-weight: 300;
  background-color: rgb(54, 54, 54);
}

.botaoCalculo{
  color: white;
  background-color: orange;
  font-size: 50px;
  border-color: black;
  border-radius: 100px;
  height: 90px;
  width: 80px;
  transform: scale(0.9);
  transition: 1s;
}

.botaoCalculo:hover{
  transition: 1s;
  background-color: rgb(255, 197, 90);
}

.botaoCalculoSuperior{
  color: black;
  background-color: grey;
  font-size: 50px;
  border-color: black;
  border-radius: 100px;
  height: 90px;
  width: 80px;
  transform: scale(0.9);
  transition: 1s;
}

.botaoCalculoSuperior:hover{
  transition: 1s;
  background-color: rgb(204, 204, 204);
}

</style>
