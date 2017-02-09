# vue-countdown
Countdown component for Vue 2.

## Installation

    npm install @nylira/vue-countdown

## Usage
Here's an example Vue 2 component.

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
Add the parameter `units='short'` for D, H, M, S labels instead of Days, Hours, Minutes, etc.
