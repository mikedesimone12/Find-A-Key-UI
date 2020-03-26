<template>
<v-container fluid fill-height>
<v-layout justify-center align-center>
  <div class="home">
      <!-- TODO: RADIO BUTTON ON BOTTOM (OR TOP RIGHT) OF PAGE TO CHANGE BUTTONS FROM FLATS TO SHARPS -->
      <h2 class ="">Option 1:</h2>
      <h3>Pick a key here to highlight the chords associated with it...</h3>
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="notes"
          label="Root Note"
        ></v-select>
        <v-spacer></v-spacer>
        <v-select
          :items="keyTypes"
          label="Type"
        ></v-select>
      </v-col>
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
  data: () => ({
    notes: ['A', 'B', 'C', 'D', 'E', 'F', 'G'],
    sharps: ['A#', 'C#', 'D#', 'F#', 'G#'],  // TODO: dynamically change to sharps and flats, and use loop or alphabetizing to position properly
    flats: ['Bb', 'Db', 'Eb', 'Gb', 'Ab'],
    keyTypes: ['Major', 'Minor']  // TODO: add harmonic minor and other exotic keys
  }),
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
