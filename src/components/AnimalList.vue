<template>
  <div>
    <tr>
      <th>vrsta</th>
      <th>ime</th>
      <th>datum rodjenja</th>
    </tr>
    <tr v-for="(animal, index) in animals" :key="index">
      <td>{{ animal.specie }}</td>
      <td>{{ animal.name }}</td>
      <td>{{ animal.birthday }}</td>
    </tr>
  </div>
</template>

<script>
export default {
  data() {
    return {
      animals: [
        {specie:"Tiger", name:"Tiger", birthday:"20.03.2010"},
        {specie:"Bear", name:"Meda", birthday:"23.08.2015"},
        {specie:"Lion", name:"Lord", birthday:"30.05.2013"},
        {specie:"Horse", name:"Marko", birthday:"15.04.2012"},
        {specie:"Cat", name:"Cica", birthday:"10.02.2018"}
      ]
    }
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
