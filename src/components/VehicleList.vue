<template>
    <div>
      <h2>Daftar Kendaraan</h2>
      <ul class="vehicle-list">
        <vehicle-item
          v-for="vehicle in vehicles"
          :key="vehicle.id"
          :vehicle="vehicle"
          @select-vehicle="showDetails"
        />
      </ul>
    </div>
  </template>
  
  <script>
  import VehicleItem from './VehicleItem.vue';
  
  export default {
    components: {
      VehicleItem,
    },
    data() {
      return {
        vehicles: [
          {
            id: 1,
            name: 'Mobil',
            description: 'Mobil nyaman dan cepat.',
            types: [
              { type: 'Sedan', description: 'Mobil jenis sedan.' },
              { type: 'SUV', description: 'Mobil jenis SUV.' },
              { type: 'Hatchback', description: 'Mobil jenis hatchback.' },
            ],
          },
          {
            id: 2,
            name: 'Motor',
            description: 'Motor cepat dan gesit.',
            types: [
              { type: 'Sport', description: 'Motor jenis sport.' },
              { type: 'Cruiser', description: 'Motor jenis cruiser.' },
              { type: 'Scooter', description: 'Motor jenis scooter.' },
            ],
          },
          {
            id: 3,
            name: 'Truk',
            description: 'Truk besar dan kuat.',
            types: [
              { type: 'Pickup', description: 'Truk jenis pickup.' },
              { type: 'Box', description: 'Truk jenis box.' },
              { type: 'Container', description: 'Truk jenis container.' },
            ],
          },
        ],
      };
    },
    methods: {
      showDetails(vehicle) {
        this.$emit('vehicle-selected', vehicle);
      },
    },
  };
  </script>
  