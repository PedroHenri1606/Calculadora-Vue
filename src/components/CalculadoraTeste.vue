<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table class="table table-hover">
      <td colspan="4">0</td> 
      <tr>
        <td>1</td>
        <td>2</td>
        <td>3</td>
        <td>+</td>
      </tr>
      <tr>
        <td>4</td>
        <td>5</td>
        <td>6</td>
        <td>-</td>
      </tr>
      <tr>
        <td>7</td>
        <td>8</td>
        <td>9</td>
        <td>*</td>
      </tr>
      <tr>
        <td>C</td>
        <td>0</td>
        <td>X</td>
        <td>/</td>
      </tr>
    </table>
    
  </div>
</template>

<script>
export default {
  name: 'CalculadoraTeste',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
