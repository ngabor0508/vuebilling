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
        <tr v-for="row in rows" v-bind:key="row.title">
          <td>{{ row.title }}</td>
          <td>{{ row.price }}</td>
          <td>{{ row.quantity }}</td>
          <td>
            <button @click="deleteEvent(row.title)" id="delete">X</button>
            <button id="edit">Edit</button>
          </td>
          <td>{{ row.price * row.quantity }}</td>
        </tr>

        <tr>
          <td>
            <input
              type="text"
              name="input_title"
              id="input_title"
              placeholder="Title"
              v-model="newrow.title"
            />
          </td>
          <td>
            <input
              type="number"
              name="input_price"
              id="input_price"
              placeholder="Price"
              v-model="newrow.price"
            />
          </td>
          <td>
            <input
              type="number"
              name="input_quantity"
              id="input_quantity"
              placeholder="Quantity"
              v-model="newrow.quantity"
            />
          </td>
          <button @click="addRow()" name="input_add" id="input_add">Add</button>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  methods: {
    deleteEvent(title) {
      this.rows = this.rows.filter((e) => e.title !== title);
    },
    addRow(){
      this.rows.push({title: this.newrow.title, price: this.newrow.price, quantity: this.newrow.quantity});
    },
    edit() {},
  },
  data() {
    return {
      newrow:
         {
          title: "",
          price: 0,
          quantity: 0,
        },
        
      rows: [
        {
          title: "Kerék",
          price: 100,
          quantity: 12,
        },
        {
          title: "Teleszkóp",
          price: 1000,
          quantity: 300,
        },
        {
          title: "Kormány",
          price: 230,
          quantity: 5,
        },
        {
          title: "Ajtó",
          price: 45120,
          quantity: 321,
        },
      ],
    };
  },
};
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
