<template>
    <div>
      <h1>Sensor Data</h1>
      <p>Current Pressure: {{ pressure }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'PressureSensor',
    data() {
      return {
        pressure: 0,
      };
    },
    created() {
      this.connectToWebSocket();
    },
    methods: {
      connectToWebSocket() {
        const socket = new WebSocket('ws://localhost:8000/ws/pressure/');
        
        socket.onmessage = (event) => {
          const data = JSON.parse(event.data);
          console.log(data)
          this.pressure = data.pressure;
        };
  
        socket.onclose = (event) => {
          console.error('WebSocket closed unexpectedly', event);
        };
  
        socket.onerror = (error) => {
          console.error('WebSocket error', error);
        };
      },
    },
  };
  </script>
  
  <style>
 
  </style>