<template>
    <div class="vehicle-type" @click="selectType">
      <h4>{{ type.type }}</h4>
      <p>{{ type.description }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      type: Object,
    },
    methods: {
      selectType() {
        this.$emit('select-type', this.type);
      },
    },
  };
  </script>
  
  <style scoped>
  .vehicle-type {
    padding: 10px;
    background: #e0f7fa;
    margin: 5px 0;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  .vehicle-type:hover {
    background: #b2ebf2;
  }
  .vehicle-type h4 {
    margin: 0;
    color: #00796b;
  }
  .vehicle-type p {
    margin: 5px 0 0;
    color: #004d40;
  }
  </style>
  