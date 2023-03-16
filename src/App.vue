<script>
export default {
  name: 'App',
  data() {
    return {
      data: new Date(),
      horas: 0,
      minutos: 0,
      segundos: 0,
    };
  },
  methods: {
    updateClock() {
      const date = new Date();
      this.horas = String(date.getHours()).padStart(2, '0');
      this.minutos = String(date.getMinutes()).padStart(2, '0');
      this.segundos = String(date.getSeconds()).padStart(2, '0');
    }
  },
  mounted() {
    this.updateClock();
    setInterval(this.updateClock, 1000)
  }
}
</script>

<template>
  <body>
    <span>{{ this.horas }} : {{ this.minutos }} : {{ this.segundos }}</span>
  </body>
</template>

<style scoped>
span {
  font-size: 8vw;
  color: lightcoral;
  background-color: rgba(0, 0, 0, 0.8);
  border-radius: 10px;
  padding: 0 30px;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
