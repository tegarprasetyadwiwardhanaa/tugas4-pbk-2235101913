<template>
  <div id="app">
    <vehicle-list @vehicle-selected="displayDetails"></vehicle-list>
    <vehicle-details :vehicle="selectedVehicle">
      <template v-slot:additional-info="slotProps">
        <div v-if="slotProps.type.type === 'Sedan'">
          <p>Warna: Merah</p>
          <p>Kapasitas: 4 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Sedan</button>
        </div>
        <div v-else-if="slotProps.type.type === 'SUV'">
          <p>Warna: Hitam</p>
          <p>Kapasitas: 7 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan SUV</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Hatchback'">
          <p>Warna: Biru</p>
          <p>Kapasitas: 5 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Hatchback</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Sport'">
          <p>Warna: Kuning</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Sport</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Cruiser'">
          <p>Warna: Hitam</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Cruiser</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Scooter'">
          <p>Warna: Putih</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Scooter</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Pickup'">
          <p>Warna: Merah</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Pickup</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Box'">
          <p>Warna: Biru</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Box</button>
        </div>
        <div v-else-if="slotProps.type.type === 'Container'">
          <p>Warna: Hijau</p>
          <p>Kapasitas: 2 orang</p>
          <button @click="bookVehicle(slotProps.type.type)">Pesan Container</button>
        </div>
      </template>
    </vehicle-details>
  </div>
</template>

<script>
import VehicleList from './components/VehicleList.vue';
import VehicleDetails from './components/VehicleDetails.vue';

export default {
  components: {
    VehicleList,
    VehicleDetails,
  },
  data() {
    return {
      selectedVehicle: null,
    };
  },
  methods: {
    displayDetails(vehicle) {
      this.selectedVehicle = vehicle;
    },
    bookVehicle(type) {
      alert(`Kendaraan tipe ${type} berhasil dipesan!`);
    },
  },
};
</script>

<style scoped>
</style>
