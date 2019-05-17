<template>
  <div id="wrapper">
    <a href="#" class="menu-icon" @click.prevent="showMenu">
      <svg aria-hidden="true" focusable="false" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="currentColor" d="M442 114H6a6 6 0 0 1-6-6V84a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6zm0 160H6a6 6 0 0 1-6-6v-24a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6zm0 160H6a6 6 0 0 1-6-6v-24a6 6 0 0 1 6-6h436a6 6 0 0 1 6 6v24a6 6 0 0 1-6 6z" class=""></path></svg>
    </a>

    <Counter class="p2" :class="p2Color" v-if="numPlayers > 1"></Counter>

    <Counter :class="p1Color"></Counter>

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
          <label class="p2" :class="{ 'active': numPlayers > 1 }">
            <input type="radio" name="players" value="2" v-model="numPlayers">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 659 512">
              <path fill="currentColor" d="M206 256a112 112 0 1 0 0-224 112 112 0 0 0 0 224zm77 32h-8a158 158 0 0 1-137 0h-9c-63 0-115 52-115 115v29c0 27 22 48 48 48h288c27 0 48-21 48-48v-29c0-63-52-115-115-115z"/>
              <path fill="currentColor" d="M378 480c27 0 48-21 48-48v-29c0-53-36-98-85-111 10-3 20-4 30-4h9a158 158 0 0 0 137 0h8c63 0 115 52 115 115v29c0 27-21 48-48 48H378zm70-224a112 112 0 1 0 0-224 112 112 0 0 0 0 224z"/>
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
      </div>
    </div>

    <div class="credits">
      <a href="https://twitter.com/kevinn">By @kevinn </a> | <a href="https://github.com/elintseeker/lifecounter">Github</a>
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
      p2Color: 'bg-green'
    }
  },
  methods: {
    showMenu: function() {
      const body = document.getElementById('menu');
      body.classList.toggle('open');
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

    background-color: rgba(0,0,0,0.88);
  }

  &.open {
    display: block;
    transform: translateY(0);
  }

  h2 {
    margin: 0 0 8px;
    font-size: 18px;
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
      .p1, .p2 {
        margin-right: 16px;
        cursor: pointer;

        svg {
          display: block;
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
</style>