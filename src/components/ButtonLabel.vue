<template>
  <div class="root">
    <button v-on:click="count_make" v-on:dblclick="is_palindrome">
      <div class="cont-elems">

        <div>
          <svg xmlns="http://www.w3.org/2000/svg" class="octicon octicon-repo-forked v-align-text-bottom" aria-hidden="true" viewBox="0 0 10 16" width="10" height="16" version="1.1"><path fill-rule="evenodd" d="M 8 1 a 1.993 1.993 0 0 0 -1 3.72 V 6 L 5 8 L 3 6 V 4.72 A 1.993 1.993 0 0 0 2 1 a 1.993 1.993 0 0 0 -1 3.72 V 6.5 l 3 3 v 1.78 A 1.993 1.993 0 0 0 5 15 a 1.993 1.993 0 0 0 1 -3.72 V 9.5 l 3 -3 V 4.72 A 1.993 1.993 0 0 0 8 1 Z M 2 4.2 C 1.34 4.2 0.8 3.65 0.8 3 c 0 -0.65 0.55 -1.2 1.2 -1.2 c 0.65 0 1.2 0.55 1.2 1.2 c 0 0.65 -0.55 1.2 -1.2 1.2 Z m 3 10 c -0.66 0 -1.2 -0.55 -1.2 -1.2 c 0 -0.65 0.55 -1.2 1.2 -1.2 c 0.65 0 1.2 0.55 1.2 1.2 c 0 0.65 -0.55 1.2 -1.2 1.2 Z m 3 -10 c -0.66 0 -1.2 -0.55 -1.2 -1.2 c 0 -0.65 0.55 -1.2 1.2 -1.2 c 0.65 0 1.2 0.55 1.2 1.2 c 0 0.65 -0.55 1.2 -1.2 1.2 Z" /></svg>
        </div>

        <div>
          Fork
        </div>

      </div>
    
    </button>

    <span>{{count_btn}}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count_btn: 0
    }
  },
  methods: {
    count_make() {
      this.count_btn += 1
    },
    
    is_palindrome() {
      const str = `${this.count_btn}`

      if(str.length === 1) return
      console.log(this.palindrome(str))
    },

    palindrome(str) {
      const s = str.toLowerCase().replace(/[\W_]/g, '');
      return s === [...s].reverse().join('');
    }
  }
}
</script>

<style scoped>
.root {
  /* background-color: red; */
  display: flex;
  font-size: 12px;
  font-weight: 600;
  white-space: nowrap;
  cursor: pointer;
}
.root > * {
  display: flex;
  flex: 1;
  justify-content: center;
  align-items: center;
}
  button {
    padding: 3px 10px;
    border-radius: .25em;
    border-bottom-right-radius: 0px;
    border-top-right-radius: 0px;

    background-color:#eff3f6;
    background-image: linear-gradient(-180deg, rgb(250, 251, 252), rgb(239, 243, 246) 90%);
    background-position: -1px -1px;
    background-repeat: repeat-x;
    background-size: 110% 110%;

    border: 1px solid rgba(27,31,35,.2);
    
    cursor: inherit;
    color:#24292e;
    font-family: inherit;
    font-size: inherit;
    font-weight: inherit;

    /* Not requisite because of FLEX. */
    /* line-height: 20px;  */

    /* The Button element is currently in use (The 'Double-click' correction). */
    /* -moz-appearance: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -webkit-appearance: none;
    -webkit-user-select: none;
    appearance: none; */
  }
  button:hover {
    background-color:#e6ebf1;
    background-image: linear-gradient(-180deg, rgb(240, 243, 246), rgb(230, 235, 241) 90%);
    background-position: -.5em;
    border-color:rgba(27,31,35,.35);
  }
  button:active {
    background-color:#e9ecef;
    background-image: none;
    border-color:rgba(27,31,35,.35);
    box-shadow: inset 0px 0.15em 0.3em rgba(27,31,35,0.15);
  }
  button:focus {
    box-shadow: 0px 0px 0px 0.2em rgba(3,102,214,0.3);
    outline: 0;
  }

  svg {
    fill: currentColor;
    display: flex;
    padding: 2px;
  }

    .cont-elems {
      display: flex;
      flex: 1;
    }
    .cont-elems > div {
      /* border: 1px solid red; */
      display: flex;
      flex: 1;
      justify-content: center;
      align-items: center;
    }

    span {
      /* background-color: green; */
      padding: 3px 10px;
      background-color:#fff;
      border: 1px solid rgba(27,31,35,.2);
      border-bottom-right-radius: 3px;
      border-left: 0;
      border-top-right-radius: 3px;
      color:#24292e;
      /* Button:focus fix */
      z-index: -1;
    }
</style>
