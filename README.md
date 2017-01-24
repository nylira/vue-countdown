# vue-countdown
Countdown component for Vue 2.

## Usage

    <template>
      <vue-countdown date="February 28, 2017"></vue-countdown>
    </template>

    <script>
      import VueCountdown from '@nylira/vue-countdown'
      export default {
        components: {
          VueCountdown
        }
      }
    </script>

## Options
Add the parameter `units='short'` for D, H, M, S units instead of Days, Hours, Minutes, etc.
