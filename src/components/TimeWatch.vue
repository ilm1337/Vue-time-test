<script>

  export default {
    name: "TimeWatch",
    data(){
      return {
        hours: '--',
        minutes: '--',
        seconds: '--'
      }
    },
    mounted() {
      setInterval(()=> this.updateClock(), 1000)
    },
    methods: {
      addLeadingZeros(num, totalLength) {
        return String(num).padStart(totalLength, '0');
      },
      updateClock() {
        const date = new Date();
        this.hours = this.addLeadingZeros(date.getHours(), 2);
        this.minutes = this.addLeadingZeros(date.getMinutes(), 2);
        this.seconds = this.addLeadingZeros(date.getSeconds(), 2);

      }
    },
  }

</script>

<template>
  <div class="container">
    <div class="watch">
      <p>{{hours}} : {{minutes}} : {{seconds}}</p>
    </div>
  </div>
</template>


<style>
.container {
  display: flex;
  color: white;

}
.watch{
  font-family: 'Orbitron', monospace;
  font-size: 80px;
  display: inline-block;
  text-shadow: 0px 0px 8px greenyellow;
}

</style>
