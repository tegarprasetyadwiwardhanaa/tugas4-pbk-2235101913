<template>
    <li class="vehicle-item" @click="selectVehicle">
      <h3>{{ vehicle.name }}</h3>
      <p>{{ vehicle.description }}</p>
    </li>
  </template>
  
  <script>
  export default {
    props: {
      vehicle: Object,
    },
    methods: {
      selectVehicle() {
        this.$emit('select-vehicle', this.vehicle);
      },
    },
  };
  </script>
  