<template>
    <div v-if="vehicle" class="vehicle-details">
      <h2>Detail Kendaraan</h2>
      <h3>{{ vehicle.name }}</h3>
      <p>Deskripsi: {{ vehicle.description }}</p>
      <div class="types">
        <h4>Tipe-Tipe:</h4>
        <vehicle-type
          v-for="type in vehicle.types"
          :key="type.type"
          :type="type"
          @select-type="showTypeDetails"
        />
      </div>
      <div class="type-details" v-if="selectedType">
        <h4>Detail Tipe: {{ selectedType.type }}</h4>
        <p>{{ selectedType.description }}</p>
        <div class="additional-info">
          <slot name="additional-info" :type="selectedType"></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import VehicleType from './VehicleType.vue';
  
  export default {
    props: {
      vehicle: Object,
    },
    components: {
      VehicleType,
    },
    data() {
      return {
        selectedType: null,
      };
    },
    methods: {
      showTypeDetails(type) {
        this.selectedType = type;
      },
    },
  };
  </script>
  