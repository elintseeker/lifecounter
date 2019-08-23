<template>
  <div class="counter bg-blue">
    <a href="#" class="inc down" @click.prevent="minus" v-if="counter === 0" disabled>
      <svg aria-hidden="true" focusable="false" data-icon="minus-circle" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M140 274c-6.6 0-12-5.4-12-12v-12c0-6.6 5.4-12 12-12h232c6.6 0 12 5.4 12 12v12c0 6.6-5.4 12-12 12H140zm364-18c0 137-111 248-248 248S8 393 8 256 119 8 256 8s248 111 248 248zm-32 0c0-119.9-97.3-216-216-216-119.9 0-216 97.3-216 216 0 119.9 97.3 216 216 216 119.9 0 216-97.3 216-216z"></path></svg>
    </a>
    <a href="#" class="inc down" @click.prevent="minus" v-else>
      <svg aria-hidden="true" focusable="false" data-icon="minus-circle" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M140 274c-6.6 0-12-5.4-12-12v-12c0-6.6 5.4-12 12-12h232c6.6 0 12 5.4 12 12v12c0 6.6-5.4 12-12 12H140zm364-18c0 137-111 248-248 248S8 393 8 256 119 8 256 8s248 111 248 248zm-32 0c0-119.9-97.3-216-216-216-119.9 0-216 97.3-216 216 0 119.9 97.3 216 216 216 119.9 0 216-97.3 216-216z"></path></svg>
    </a>
    <span>{{ counter }}</span>
    <a href="#" class="inc up" @click.prevent="plus">
      <svg aria-hidden="true" focusable="false" data-icon="plus-circle" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M384 250v12c0 6.6-5.4 12-12 12h-98v98c0 6.6-5.4 12-12 12h-12c-6.6 0-12-5.4-12-12v-98h-98c-6.6 0-12-5.4-12-12v-12c0-6.6 5.4-12 12-12h98v-98c0-6.6 5.4-12 12-12h12c6.6 0 12 5.4 12 12v98h98c6.6 0 12 5.4 12 12zm120 6c0 137-111 248-248 248S8 393 8 256 119 8 256 8s248 111 248 248zm-32 0c0-119.9-97.3-216-216-216-119.9 0-216 97.3-216 216 0 119.9 97.3 216 216 216 119.9 0 216-97.3 216-216z" class=""></path></svg>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  },
  data() {
    return {
      counter: 20
    }
  },
  methods: {
    plus: function(){
      this.counter++;
    },
    minus: function(){
      this.counter--;
    }
  }
}
</script>

<style scoped lang="scss">
/* archivo-narrow-regular - latin */
@font-face {
  font-family: 'Archivo Narrow';
  font-style: normal;
  font-weight: 400;
  src: local('Archivo Narrow Regular'), local('ArchivoNarrow-Regular'),
       url('/fonts/archivo-narrow-v11-latin-regular.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('/fonts/archivo-narrow-v11-latin-regular.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}

.counter {
  font-family: 'Archivo Narrow', Helvetica, Roboto, Arial, sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;

  box-shadow: inset 0 0 10em rgba(0,0,0,0.5);

  > span {
    display: inline-block;
    margin: 0 16px;
    font-size: 128px;
  }

  &.p2 {
    transform: rotate(180deg);
  }

  @media (max-width: 960px) {
    > span {
      font-size: 86px;
    }
  }
}

.inc {
  display: flex;
  align-items: center;
  justify-content: center;

  padding: 8px;
  width: 50px;
  height: 50px;

  svg {
    display: block;
    width: 44px;
    height: 44px;
  }

  &[disabled] {
    pointer-events: none;
    opacity: 0.33;
  }
}
</style>