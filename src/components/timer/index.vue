<template>
  <div>
      <slot :start="start" :stop="stop" :formattedTime="formattedTime"></slot>
  </div>
</template>

<script>
export default {
    name: 'Timer',
    data() {
        return {
            timerState: 'stopped',
            currentTimer: 0,
            formattedTime: "00:00",
            ticker: undefined,
        }
    },
    methods: {
        start () {
        if (this.timerState !== 'running') {
            this.tick();
            this.timerState = 'running';
        }
        },
        tick() {
            this.ticker = setInterval(() => {
            this.currentTimer++;
            this.formattedTime = this.formatTime(this.currentTimer);
            }, 1000)
        },
        formatTime(seconds) {
            let measuredTime = new Date(null);
            measuredTime.setUTCSeconds(seconds);
            let MHSTime = measuredTime.toISOString().substr(14, 5);
            return MHSTime;
        },
        stop () {
            window.clearInterval(this.ticker)
            this.currentTimer = 0;
            this.timerState = "stopped";
        },

    },
    mounted() {
        this.start();
    }
}
</script>

<style>

</style>