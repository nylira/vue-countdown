<template>
  <div class="pz-countdown">
    <div class="block">
      <div class="value">{{ twoDigits(days) }}</div>
      <div class="unit">Days</div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(hours) }}</div>
      <div class="unit">Hours</div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(minutes) }}</div>
      <div class="unit">Minutes</div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(seconds) }}</div>
      <div class="unit">Seconds</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'pz-countdown',
  computed: {
    usableDate () {
      return Math.trunc(Date.parse(this.date) / 1000)
    },
    seconds () {
      return (this.usableDate - this.now) % 60
    },
    minutes () {
      return Math.trunc((this.usableDate - this.now) / 60) % 60
    },
    hours () {
      return Math.trunc((this.usableDate - this.now) / 60 / 60) % 24
    },
    days () {
      return Math.trunc((this.usableDate - this.now) / 60 / 60 / 24)
    }
  },
  data () {
    return {
      now: Math.trunc((new Date()).getTime() / 1000)
    }
  },
  methods: {
    twoDigits (number) {
      if (number < 10) return '0' + number
      else return number
    }
  },
  mounted () {
    window.setInterval(() => {
      this.now = Math.trunc((new Date()).getTime() / 1000)
    }, 1000)
  },
  props: ['date']
}
</script>

<style src="./style.css"></style>
