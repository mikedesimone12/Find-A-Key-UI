<template>
<v-container fluid fill-height>
<v-layout justify-center align-center>
  <div class="home">
      <!-- TODO: RADIO BUTTON ON BOTTOM (OR TOP RIGHT) OF PAGE TO CHANGE BUTTONS FROM FLATS TO SHARPS -->
      <h2>Option 1:</h2>
      <h3>Pick a key here to highlight the chords associated with it...</h3>
      <ul>
      <label for="key_notes">Choose a key:</label>
      <select id="key_notes">
        <option value="A">A</option>
        <option value="B">B</option>
        <option value="C">C</option>
        <option value="D">D</option>
        <option value="E">A</option>
        <option value="F">B</option>
        <option value="G">C</option>
      <!-- TODO: add sharps and flats -->
      </select>
      <select id="key_type">
        <option value="Major">Major</option>
        <option value="Minor">Minor</option>
      </select>
      </ul>
      <br><h2>Option 2:</h2>
      <h3>Click up to seven chords, and the list will narrow down what keys they could be in...</h3><br>
      <h4>Major Chords</h4> <!--buttons grid here--> 
      <div class="chords">
        <button>A</button>
        <button>A#</button> <!-- change to Bb based on radio button choice -->
        <button>B</button>
      </div><br>
      <h4>Minor Chords</h4> <!--buttons grid here-->
      <div class="chords">
        <button>Am</button>
        <button>A#m</button> <!-- change to Bb based on radio button choice -->
        <button>Bm</button>
        <button>Cm</button>
      </div><br>
      <h4>Dominant 7 Chords</h4> <!-- change to vue buttons that are fancier -->
      <div class="chords">
        <button>A7</button>
        <button>A#7</button> <!-- change to Bb based on radio button choice -->
      </div>
      <br><br>
      <div>
     <h2>Possible Keys:</h2>
      <h4><i>Dynamically adding the keys here...</i></h4>
      <h4>Key of G major</h4>
      <h4>Key of E minor</h4>
      <h4>Key of A major</h4>
      <h4>Key of F# minor</h4>
      <h4>Key of D major</h4>
      <h4>Key of B minor</h4>
      </div>
  </div>
  </v-layout>
  </v-container>
</template>

<script>

export default {
  name: 'Home',
}
</script>
<style scoped>
h1, h2 {
  font-weight: normal;
  color: black;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: blueviolet;
}
.chords{
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-auto-rows: minmax(50px, auto);
}
</style>
