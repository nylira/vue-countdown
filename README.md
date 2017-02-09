# vue-countdown
Countdown component for Vue 2.

## Installation

    npm install @nylira/vue-countdown

## Usage

    <template>
      <countdown date="February 28, 2017"></countdown>
    </template>

    <script>
      import Countdown from '@nylira/vue-countdown'
      export default {
        components: {
          Countdown
        }
      }
    </script>

    <style>
      .ny-countdown {
        width: 320px;
      }
    </style>

## Parameters

    <countdown units="short"></countdown>
    // for D, H, M, S labels instead of Days, Hours, Minutes, Seconds
