<template>
  <div id="app">
    <a href="https://github.com/RichardLindsay/scotrail-excuse-generator" target="_blank" class="octocat"><img src="./assets/octocat.svg"/></a>
    <img id="logo" src="./assets/logo.svg"/>
    <p v-bind:class="{ excuse: show_excuse }">{{ excuse }}</p>
    <a class="button" href="#" v-on:click.prevent="generate()"><span>Generate</span></a>
    <a href="https://twitter.com/hashtag/scotfail" target="_blank">#scotfail</a>

  </div>
</template>

<script>
export default {
  name: 'App',
  data: function () {
    return {
      link: 'https://twitter.com/hashtag/scotfail',
      reasons: [
        'ScotRail apologises for the late running of this service; this is due to ',
        'ScotRail apologises for the historic lack of investment; this is due to ',
        'ScotRail apologises for the cancellation of this service; this is due to ',
        'ScotRail apologises for the inconvenience; this is due to '
      ],
      excuses: [
        'it being too windy.',
        'it being too sunny.',
        'it being too dry.',
        'it being too cold.',
        'it being too rainy.',
        'it being too overcast.',
        'there being too many late running trains in front of this one.',
        'there not being enough renewable electricity.',
        'it being too foggy.',
        'there being too many leaves in the World.',
        'there being too many trains requiring maintenance.',
        'the tracks being too hot.',
        'no step free access.',
        'a fault on the train that we need to repair.',
        'there being too many passengers.',
        'a points failure in the middle of nowhere.',
        'trampolines.',
        'cows on the line.',
        'there being too few carriages.',
        'the waves being too high.',
        'the tracks being slightly wet.',
        'the train crew being out of position.',
        'multiple signals reflecting in the curved windscreen when driving at night.',
        'a naked trespasser on the tracks.',
        'an air leak on a train that needs to be repaired.'
      ],
      excuse: 'Click below to generate an excuse...',
      show_excuse: false
    }
  },
  methods: {
    generate: function () {
      this.excuse = this.reasons[Math.floor(Math.random() * this.reasons.length)] + this.excuses[Math.floor(Math.random() * this.excuses.length)]
      this.show_excuse = true
    }
  }
}
</script>

<style>
body{
  margin: 0 40px;
}
#app {
  align-items: center;
  display: flex;
  flex-direction: column;
  font-family: 'Source Sans Pro';
  font-size: 20px;
  justify-content: center;
  margin: 0 auto;
  max-width: 1280px;
  min-height: 100vh;
}
#logo {
  display: block;
  margin-bottom: 2em;
  max-width: 300px;
  width: 100%;
}
p {
  color: #999999;
  font-size: 25px;
  margin: 0 0 4em 0;
  text-align: center;
  word-break: break-word;
}
p.excuse{
  color: #002664;
}
a {
  color: #999999;
  margin: 1em 0;
  text-decoration: none;
  transition: 200ms all;
}
a:hover {
  color: #002664;
}
.button {
  align-items: center;
  background-color: #f8fae4;
  background-image: url('./assets/ticket_bg.png');
  border-radius: 5px;
  box-shadow: 4px 4px 30px 0px darkgrey;
  color: #000;
  display: inline-flex;
  font-family: 'Press Start 2P';
  font-size: 9px;
  height: 85px;
  margin: 0;
  overflow: hidden;
  padding: 0 4em;
  position: relative;
  text-align: center;
  text-decoration: none;
  transform: rotate(3deg);
}
.button::before{
  background-color: #fc4732;
  content: '';
  display: block;
  height: 17px;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}
.button::after{
  background-color: #fc4732;
  bottom: 0;
  content: '';
  display: block;
  height: 17px;
  left: 0;
  position: absolute;
  width: 100%;
}
.button:hover {
  color: #000;
}
.button:hover span::before {
  display: block;
}
.button span::before {
  background-color: #fff;
  border-radius: 50%;
  box-shadow: inset 1px 0px 2px 0px black;
  content: '';
  display: none;
  height: 10px;
  position: absolute;
  right: 7px;
  top: 12px;
  width: 10px;
}
.octocat {
  position: fixed;
  top: 20px;
  right: 20px;
  margin: 0;
}

@media (min-width: 960px) {
  body {
    margin: 0;
  }
  #logo {
    max-width: none;
    width: auto;
  }
  p {
    font-size: 80px;
    margin-bottom: 1em;
  }
  a {
    font-size: 24px;
  }
  .button {
    font-size: 18px;
    height: 175px;
    padding: 0 4em;
  }
  .button:hover {
    transform: translateY(-10px) rotate(3deg);
  }
  .button::before {
    height: 35px;
  }
  .button::after{
    height: 35px;
  }
  .button span::before {
    box-shadow: inset 2px 1px 5px 0px black;
    height: 20px;
    right: 15px;
    top: 25px;
    width: 20px;
  }
}
</style>
