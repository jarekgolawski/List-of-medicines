<template>
  <div id="app">
    <Header />
    <AddMedicine v-on:add-medicine="addMedicine" />
    <Medicines v-bind:medicines="medicines" 
    v-on:del-medicine="deleteMedicine"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Medicines from './components/Medicines';
import AddMedicine from './components/AddMedicine';

export default {
  name: 'app',
  components: {
    Header,
    Medicines,
    AddMedicine
  },
  data() {
    return {
     medicines: [
       {
         id: 1,
         title: "Witamina C",
         availability: false
       },
       {
         id: 2,
         title: "Witamina D",
         availability: false
       },
       {
         id: 3,
         title: "Nervosol",
         availability: false
       }
     ]
    }
  },
  methods: {
    deleteMedicine(id) {
      this.medicines = this.medicines.filter(medicine => medicine.id !== id);
    },
    addMedicine(newMedicine) {
      this.medicines = [...this.medicines, newMedicine];
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }
</style>
