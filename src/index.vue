<template>
  <div class="pz-countdown">
    <div class="block">
      <div class="value">{{ twoDigits(days) }}</div>
      <div class="unit">
        <template v-if="units === 'short'">D</template>
        <template v-else>Days</template>
      </div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(hours) }}</div>
      <div class="unit">
        <template v-if="units === 'short'">H</template>
        <template v-else>Hours</template>
      </div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(minutes) }}</div>
      <div class="unit">
        <template v-if="units === 'short'">M</template>
        <template v-else>Minutes</template>
      </div>
    </div>
    <div class="block">
      <div class="value">{{ twoDigits(seconds) }}</div>
      <div class="unit">
        <template v-if="units === 'short'">S</template>
        <template v-else>Seconds</template>
      </div>
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
  props: ['date', 'units']
}
</script>

<style src="./style.css"></style>
