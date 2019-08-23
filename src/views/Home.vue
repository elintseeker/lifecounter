<template>
  <div id="wrapper" :class="{ 'p4': numPlayers > 2 }">
    <a href="#" class="menu-icon" @click.prevent="showMenu">
      <svg aria-hidden="true" focusable="false" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="currentColor" d="M442 114H6a6 6 0 0 1-6-6V84a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6zm0 160H6a6 6 0 0 1-6-6v-24a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6zm0 160H6a6 6 0 0 1-6-6v-24a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6z" class=""></path></svg>
    </a>

    <Counter class="p4" :class="p4Color" v-if="numPlayers > 2" ref="counters4"></Counter>

    <Counter class="p3" :class="p3Color" v-if="numPlayers > 2" ref="counters3"></Counter>

    <Counter class="p2" :class="p2Color" v-if="numPlayers > 1" ref="counters2"></Counter>

    <Counter :class="p1Color" ref="counters"></Counter>

    <div id="menu" class="menu" @click="showMenu">
      <div class="menu-wrapper">
        <h2>Players</h2>
        <div class="menu-item players">
          <label class="p1" :class="{ 'active': numPlayers == 1 }">
            <input type="radio" name="players" value="1" v-model="numPlayers">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
              <path fill="currentColor" d="M256 256a112 112 0 1 0 0-224 112 112 0 0 0 0 224zm77 32h-8a158 158 0 0 1-137 0h-9c-63 0-115 52-115 115v29c0 27 22 48 48 48h288c27 0 48-21 48-48v-29c0-63-52-115-115-115z"/>
            </svg>
          </label>
          <label class="p2" :class="{ 'active': numPlayers == 2 }">
            <input type="radio" name="players" value="2" v-model="numPlayers">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 659 512">
              <path fill="currentColor" d="M206 256a112 112 0 1 0 0-224 112 112 0 0 0 0 224zm77 32h-8a158 158 0 0 1-137 0h-9c-63 0-115 52-115 115v29c0 27 22 48 48 48h288c27 0 48-21 48-48v-29c0-63-52-115-115-115z"/>
              <path fill="currentColor" d="M378 480c27 0 48-21 48-48v-29c0-53-36-98-85-111 10-3 20-4 30-4h9a158 158 0 0 0 137 0h8c63 0 115 52 115 115v29c0 27-21 48-48 48H378zm70-224a112 112 0 1 0 0-224 112 112 0 0 0 0 224z"/>
            </svg>
          </label>
          <label class="p4" :class="{ 'active': numPlayers > 2 }">
            <input type="radio" name="players" value="4" v-model="numPlayers">
            <svg viewBox="0 0 512 512" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2">
              <g fill-rule="nonzero">
                <path d="M138.4 344.6a57.6 57.6 0 0 0 57.3-57.3 57.6 57.6 0 0 0-57.3-57.3A57.6 57.6 0 0 0 81 287.3a57.6 57.6 0 0 0 57.3 57.3zm39.4 16.4h-4.1a81 81 0 0 1-70.1 0H99A59.2 59.2 0 0 0 40 420v14.8a24.6 24.6 0 0 0 24.6 24.6H212a24.3 24.3 0 0 0 24.6-24.6V420a59.2 59.2 0 0 0-59-58.9z"/>
                <path d="M103.6 183.8a81 81 0 0 0 70.1 0h4a59.2 59.2 0 0 1 59 58.8v14.9c0 12.4-8.8 22.4-20.6 24.2a78.1 78.1 0 0 0-77.7-76.1 78.1 78.1 0 0 0-77.7 76.1A24.6 24.6 0 0 1 40 257.5v-14.9A59.2 59.2 0 0 1 99 183.8h4.6zm34.8-16.4a57.6 57.6 0 0 0 57.3-57.4 57.6 57.6 0 0 0-57.3-57.3A57.6 57.6 0 0 0 81 110a57.6 57.6 0 0 0 57.3 57.4z"/>
                <g>
                  <path d="M373.6 344.6a57.6 57.6 0 0 0 57.3-57.3 57.6 57.6 0 0 0-57.3-57.3 57.6 57.6 0 0 0-57.3 57.3 57.6 57.6 0 0 0 57.3 57.3zM413 361h-4a81 81 0 0 1-70.2 0h-4.6a59.2 59.2 0 0 0-58.9 58.9v14.8a24.6 24.6 0 0 0 24.6 24.6h147.4a24.3 24.3 0 0 0 24.6-24.6V420A59.2 59.2 0 0 0 413 361z"/>
                  <path d="M338.8 183.8a81 81 0 0 0 70.1 0h4.1a59.2 59.2 0 0 1 58.9 58.8v14.9c0 12.4-8.7 22.4-20.6 24.2a78.1 78.1 0 0 0-77.7-76.1 78.1 78.1 0 0 0-77.7 76.1 24.6 24.6 0 0 1-20.6-24.2v-14.9a59.2 59.2 0 0 1 59-58.8h4.5zm34.8-16.4A57.6 57.6 0 0 0 431 110a57.6 57.6 0 0 0-57.3-57.3 57.6 57.6 0 0 0-57.3 57.3 57.6 57.6 0 0 0 57.3 57.4z"/>
                </g>
              </g>
            </svg>
          </label>
        </div>

        <h2>1P color</h2>
        <div class="menu-item colors">
          <label><input type="radio" name="p1color" value="bg-blue"   v-model="p1Color"><span class="color bg-blue"></span></label>
          <label><input type="radio" name="p1color" value="bg-green"  v-model="p1Color"><span class="color bg-green"></span></label>
          <label><input type="radio" name="p1color" value="bg-red"    v-model="p1Color"><span class="color bg-red"></span></label>
          <label><input type="radio" name="p1color" value="bg-black"  v-model="p1Color"><span class="color bg-black"></span></label>
        </div>

        <div v-if="numPlayers > 1">
          <h2>2P color</h2>
          <div class="menu-item colors">
            <label><input type="radio" name="p2color" value="bg-blue"   v-model="p2Color"><span class="color bg-blue"></span></label>
            <label><input type="radio" name="p2color" value="bg-green"  v-model="p2Color"><span class="color bg-green"></span></label>
            <label><input type="radio" name="p2color" value="bg-red"    v-model="p2Color"><span class="color bg-red"></span></label>
            <label><input type="radio" name="p2color" value="bg-black"  v-model="p2Color"><span class="color bg-black"></span></label>
          </div>
        </div>

        <div v-if="numPlayers > 2">
          <h2>3P color</h2>
          <div class="menu-item colors">
            <label><input type="radio" name="p3color" value="bg-blue"   v-model="p3Color"><span class="color bg-blue"></span></label>
            <label><input type="radio" name="p3color" value="bg-green"  v-model="p3Color"><span class="color bg-green"></span></label>
            <label><input type="radio" name="p3color" value="bg-red"    v-model="p3Color"><span class="color bg-red"></span></label>
            <label><input type="radio" name="p3color" value="bg-black"  v-model="p3Color"><span class="color bg-black"></span></label>
          </div>
        </div>

        <div v-if="numPlayers > 2">
          <h2>4P color</h2>
          <div class="menu-item colors">
            <label><input type="radio" name="p4color" value="bg-blue"   v-model="p4Color"><span class="color bg-blue"></span></label>
            <label><input type="radio" name="p4color" value="bg-green"  v-model="p4Color"><span class="color bg-green"></span></label>
            <label><input type="radio" name="p4color" value="bg-red"    v-model="p4Color"><span class="color bg-red"></span></label>
            <label><input type="radio" name="p4color" value="bg-black"  v-model="p4Color"><span class="color bg-black"></span></label>
          </div>
        </div>

        <br />

        <a href="#" @click.prevent="resetCounters" class="reset">Reset counters</a>
      </div>
    </div>

    <div class="credits">
      <small><a href="https://twitter.com/kevinn">By @kevinn</a> | <a href="https://github.com/elintseeker/lifecounter">Github</a></small>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Counter from '@/components/counter.vue';

export default {
  name: 'home',
  components: {
    Counter
  },
  data(){
    return {
      numPlayers: 1,
      p1Color: 'bg-blue',
      p2Color: 'bg-green',
      p3Color: 'bg-red',
      p4Color: 'bg-black'
    }
  },
  methods: {
    showMenu: function() {
      const body = document.getElementById('menu');
      body.classList.toggle('open');
    },
    resetCounters: function() {     
      this.$refs.counters.counter = '20';
      this.$refs.counters2.counter = '20';
      this.$refs.counters3.counter = '20';
      this.$refs.counters4.counter = '20';
    }
  }
}
</script>

<style lang="scss" scoped>
#wrapper {
  position: fixed;
  top: 0; left: 0;
  right: 0; bottom: 0;

  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: stretch;

  > div {
    flex: 1;
  }

  &.p4 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-row: auto auto;

    .counter {
      box-sizing: border-box;
      transform: rotate(0deg);
    }

    @media (max-width: 480px) {
      display: flex;
    }
  }
}

.menu-icon {
  position: fixed;
  top: 16px; right: 8px;
  z-index: 300;

  width: 44px;
  height: 44px;

  svg {
    display: block;
    width: 32px;
    height: 32px;
  }
}

.menu {
  position: fixed;
  top: 0; right: 0; bottom: 0; left: 0;
  z-index: 200;
    transform: translateY(-100%);
    transition: transform 300ms ease-out;

  .menu-wrapper {
    position: fixed;
    top: 0; left: 0; right: 0;
    padding: 32px;

    background-color: rgba(0,0,0,0.95);
  }

  &.open {
    display: block;
    transform: translateY(0);
  }

  h2 {
    margin: 0 0 8px;
    font-size: 16px;
    font-weight: 300;
    text-align: left;
  }

  .menu-item {
    display: flex;
    align-items: center;

    margin-bottom: 16px;

    &.players,
    &.colors {
      overflow: hidden;

      label {
        display: inline-flex;
        align-items: center;
        justify-content: center;

        width: 44px;
        height: 44px;

        position: relative;
        overflow: hidden;
      }

      input {
        position: absolute;
        left: -999px;
      }
    }

    &.players {
      .p1, .p2, .p4 {
        margin-right: 16px;
        cursor: pointer;

        svg {
          display: block;
          fill: #fff;
          width: 34px;
          height: 34px;
        }

        opacity: 0.33;
      }

      .p2 {
        svg {
          width: auto;
          height: 44px;
        }
      }

      .active {
        opacity: 1;
      }
    }

    &.colors {
      input:checked + span {
        border-color: #eee;
      }
    }
  }

  .color {
    display: block;
    width: 38px;
    height: 38px;
    border: 4px solid #222;
  }
}

.credits {
  position: fixed;
  z-index: 200;
  bottom: 16px;
  left: 16px;
  font-size: 14px;
}


.reset { 
  color: #c22; 
  font-weight: 700; 
}
</style>