<template>
  <div>
    <form @submit.prevent="addItem">
      <div>
        <label>Vrsta:</label>
        <input type="text" v-model="animal.specie"  />
        <label>Ime:</label>
        <input type="text" v-model="animal.name" />
        <label>Rodjendan:</label>
        <input type="text" v-model="animal.birthday">
      </div>
      <button type="submit">add</button>
    </form>
    <table>
      <tr>
        <th>vrsta</th>
        <th>ime</th>
        <th>datum rodjenja</th>
      </tr>
      <tr v-for="(animal, index) in animals" :key="index">
        <td>{{ animal.specie }}</td>
        <td>{{ animal.name }}</td>
        <td> {{animal.birthday || 'Nepoznat'}}</td>
        <button @click="removeItem(index)">Remove</button>
        <button @click="moveToTop(index)">Move to top</button>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      animals: [
        {specie:"Tiger", name:"Tiger", birthday:"20.03.2010"},
        {specie:"Bear", name:"Meda", birthday:"23.08.2015"},
        {specie:"Lion", name:"Lord", birthday:""},
        {specie:"Horse", name:"Marko", birthday:"15.04.2012"},
        {specie:"Cat", name:"Cica", birthday:"10.02.2018"}
      ],
      animal: {
        name: '',
        birthday: '',
        specie: ''
      }
    }
  },

  methods: {
    removeItem(index) {
      this.animals.splice(index, 1)
    },
    moveToTop(index) {
      const animal = this.animals[index];
      this.animals.splice(index,1);
      this.animals = [
        animal,
        ...this.animals
      ]
    },
    addItem() {
      this.animals.push({...this.animal})
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
