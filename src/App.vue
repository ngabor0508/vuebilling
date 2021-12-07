<template>
  <div id="app">
    <table>
      <thead>
        <tr>
          <th>Title</th>
          <th>Price</th>
          <th>Quantity</th>
          <th>Operations</th>
          <th>Összérték</th>
        </tr>
      </thead> 
      
      <tbody>
        <tr v-for="row in rows"
          v-bind:key="row.title">

          <td>{{ row.title }}</td>
          <td>{{ row.price }}</td>
          <td>{{ row.quantity }}</td>
          <td>
            <button>X</button>
            <button>Edit</button>
          </td>
          <td>{{ row.price * row.quantity }} </td>
        </tr>

        <tr>
          <td><input type="text" name="input_title" id="input_title" placeholder="Title"></td>
          <td><input type="number" name="input_price" id="input_price" placeholder="Price"></td>
          <td><input type="number" name="input_quantity" id="input_quantity" placeholder="Quantity"></td>
          <button name="input_add" id="input_add">Add</button>
        </tr>



      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      rows: [
        {
          title: 'Kerék',
          price: 100,
          quantity: 12
        },
        {
          title: 'Teleszkóp',
          price: 1000,
          quantity: 300
        },
        {
          title: 'Kormány',
          price: 230,
          quantity: 5
        },
        {
          title: 'Ajtó',
          price: 45120,
          quantity: 321
        },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
