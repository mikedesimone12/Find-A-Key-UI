<template>
<v-container fluid fill-height>
<v-layout justify-center>
  <body>
  <div class="home">
      <br>
      <br><u><h2>Select Chords:</h2></u><br>
      <h3>Select up to seven chords to calculate what key(s) they could be in.</h3>
      <br><h3 class="font-weight-light">Click a button once to select the chord. Click the button again to deselect it.</h3>
      <br><h4>Major Chords</h4><br> 
      <div class="chords">
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('A'); playChord('A'); checkKeys();" :class="getColor('A')" v-on="on">A</v-btn> 
            </template>
            <span>Contains: A, {{sharpsFlats[1]}}, E</span>
          </v-tooltip>
       <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[0]); playChord(sharpsFlats[0]);  checkKeys();" :class="getColor(sharpsFlats[0])" v-on="on">{{sharpsFlats[0]}}</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[0]}}, D, F</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click=" addToList('B'); playChord('B'); checkKeys();" :class="getColor('B')" v-on="on">B</v-btn> 
            </template>
            <span>Contains: B, {{sharpsFlats[2]}}, {{sharpsFlats[3]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click=" addToList('C'); playChord('C'); checkKeys();" :class="getColor('C')" v-on="on">C</v-btn> 
            </template>
            <span>Contains: C, E, G</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click=" addToList(sharpsFlats[1]); playChord(sharpsFlats[1]); checkKeys();" :class="getColor(sharpsFlats[1])" v-on="on">{{sharpsFlats[1]}}</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[1]}}, F, {{sharpsFlats[4]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('D'); playChord('D'); checkKeys();" :class="getColor('D')" v-on="on">D</v-btn> 
            </template>
            <span>Contains: D, {{sharpsFlats[3]}}, A</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[2]); playChord(sharpsFlats[2]);  checkKeys();" :class="getColor(sharpsFlats[2])" v-on="on">{{sharpsFlats[2]}}</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[2]}}, G, {{sharpsFlats[0]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('E'); playChord('E'); checkKeys(); " :class="getColor('E')" v-on="on">E</v-btn> 
            </template>
            <span>Contains: E, {{sharpsFlats[4]}}, B</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('F'); playChord('F');  checkKeys();" :class="getColor('F')" v-on="on">F</v-btn> 
            </template>
            <span>Contains: F, A, C</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[3]); playChord(sharpsFlats[3]); checkKeys();" :class="getColor(sharpsFlats[3])" v-on="on">{{sharpsFlats[3]}}</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[3]}}, {{sharpsFlats[0]}}, {{sharpsFlats[1]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('G'); playChord('G');  checkKeys();" :class="getColor('G')" v-on="on">G</v-btn> 
            </template>
            <span>Contains: G, B, D</span>
          </v-tooltip> 
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click=" addToList(sharpsFlats[4]); playChord(sharpsFlats[4]); checkKeys();" :class="getColor(sharpsFlats[4])" v-on="on">{{sharpsFlats[4]}}</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[4]}}, C, {{sharpsFlats[2]}}</span>
          </v-tooltip>
      </div><br>
      <h4>Minor Chords</h4><br>
      <div class="chords">
        <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Am'); playChord('Am'); checkKeys();" :class="getColor('Am')" v-on="on">Am</v-btn> 
            </template>
            <span>Contains: A, C, E</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[0] + 'm'); playChord(sharpsFlats[0] + 'm'); checkKeys();" :class="getColor(sharpsFlats[0] + 'm')" v-on="on">{{sharpsFlats[0]}}m</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[0]}}, {{sharpsFlats[1]}} , F</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Bm'); playChord('Bm'); checkKeys();" :class="getColor('Bm')" v-on="on">Bm</v-btn> 
            </template>
            <span>Contains: B, D, {{sharpsFlats[3]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Cm'); playChord('Cm'); checkKeys();" :class="getColor('Cm')" v-on="on">Cm</v-btn> 
            </template>
            <span>Contains: C, {{sharpsFlats[2]}}, G</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[1] + 'm'); playChord(sharpsFlats[1] + 'm'); checkKeys();" :class="getColor(sharpsFlats[1] + 'm')" v-on="on">{{sharpsFlats[1]}}m</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[1]}}, E, {{sharpsFlats[4]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Dm'); playChord('Dm'); checkKeys();" :class="getColor('Dm')" v-on="on">Dm</v-btn> 
            </template>
            <span>Contains: D, F, A</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[2] + 'm'); playChord(sharpsFlats[2] + 'm'); checkKeys();" :class="getColor(sharpsFlats[2] + 'm')" v-on="on">{{sharpsFlats[2]}}m</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[2]}}, {{sharpsFlats[3]}}, {{sharpsFlats[0]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Em'); playChord('Em'); checkKeys();" :class="getColor('Em')" v-on="on">Em</v-btn> 
            </template>
            <span>Contains: E, G, B</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Fm'); playChord('Fm'); checkKeys();" :class="getColor('Fm')" v-on="on">Fm</v-btn> 
            </template>
            <span>Contains: F, {{sharpsFlats[4]}}, E</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[3] + 'm'); playChord(sharpsFlats[3] + 'm'); checkKeys();" :class="getColor(sharpsFlats[3] + 'm')" v-on="on">{{sharpsFlats[3]}}m</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[3]}}, A, {{sharpsFlats[1]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Gm'); playChord('Gm'); checkKeys();" :class="getColor('Gm')" v-on="on">Gm</v-btn> 
            </template>
            <span>Contains: G, {{sharpsFlats[0]}}, D</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[4] + 'm'); playChord(sharpsFlats[4] + 'm'); checkKeys();" :class="getColor(sharpsFlats[4] + 'm')" v-on="on">{{sharpsFlats[4]}}m</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[4]}}, B, {{sharpsFlats[2]}}</span>
          </v-tooltip>
      </div><br>
      <!-- TODO: dominant 7 -->
      <h4>Diminished Chords</h4><br> <!-- TODO: update tooltips for dim -->
      <div class="chords">
        <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Adim'); playChord('Adim'); checkKeys();" :class="getColor('Adim')" v-on="on">Adim</v-btn> 
            </template>
            <span>Contains: A, C, {{sharpsFlats[2]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[0] + 'dim'); playChord(sharpsFlats[0] + 'dim'); checkKeys();" :class="getColor(sharpsFlats[0] + 'dim')" v-on="on">{{sharpsFlats[0]}}dim</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[0]}}, {{sharpsFlats[1]}} , E</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Bdim'); playChord('Bdim'); checkKeys();" :class="getColor('Bdim')" v-on="on">Bdim</v-btn> 
            </template>
            <span>Contains: B, D, F</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Cdim'); playChord('Cdim'); checkKeys();" :class="getColor('Cdim')" v-on="on">Cdim</v-btn> 
            </template>
            <span>Contains: C, {{sharpsFlats[2]}}, {{sharpsFlats[3]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[1] + 'dim'); playChord(sharpsFlats[1] + 'dim'); checkKeys();" :class="getColor(sharpsFlats[1] + 'dim')" v-on="on">{{sharpsFlats[1]}}dim</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[1]}}, E, G</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Ddim'); playChord('Ddim'); checkKeys();" :class="getColor('Ddim')" v-on="on">Ddim</v-btn> 
            </template>
            <span>Contains: D, F, {{sharpsFlats[4]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[2] + 'dim'); playChord(sharpsFlats[2] + 'dim'); checkKeys();" :class="getColor(sharpsFlats[2] + 'dim')" v-on="on">{{sharpsFlats[2]}}dim</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[2]}}, {{sharpsFlats[3]}}, A</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Edim'); playChord('Edim'); checkKeys();" :class="getColor('Edim')" v-on="on">Edim</v-btn> 
            </template>
            <span>Contains: E, G, {{sharpsFlats[0]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Fdim'); playChord('Fdim'); checkKeys();" :class="getColor('Fdim')" v-on="on">Fdim</v-btn> 
            </template>
            <span>Contains: F, {{sharpsFlats[4]}}, B</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[3] + 'dim'); playChord(sharpsFlats[3] + 'dim'); checkKeys();" :class="getColor(sharpsFlats[3] + 'dim')" v-on="on">{{sharpsFlats[3]}}dim</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[3]}}, A, C</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList('Gdim'); playChord('Gdim'); checkKeys();" :class="getColor('Gdim')" v-on="on">Gdim</v-btn> 
            </template>
            <span>Contains: G, {{sharpsFlats[0]}}, {{sharpsFlats[1]}}</span>
          </v-tooltip>
          <v-tooltip bottom :disabled="!isShowingTips">
            <template v-slot:activator="{ on }">
            <v-btn @click="addToList(sharpsFlats[4] + 'dim'); playChord(sharpsFlats[4] + 'dim'); checkKeys();" :class="getColor(sharpsFlats[4] + 'dim')" v-on="on">{{sharpsFlats[4]}}dim</v-btn> 
            </template>
            <span>Contains: {{sharpsFlats[4]}}, B, D</span>
          </v-tooltip>
      </div><br>
      <b>Selected Chords: </b>
        {{this.currentChordList.join(', ')}} <!-- displaying list using this method instead of v-for, so it is properly comma separated -->
        <br>
    <div :class="{'green--text' : this.currentChordList.length <= 4, 'orange--text' : this.currentChordList.length > 4 && this.currentChordList.length <= 6, 'red--text' : this.currentChordList.length == 7}">
     <br><i>Chord Count: {{this.currentChordList.length}} </i></div><br>
      <u><h3>Possible Keys:</h3></u><br>
      <v-row justify="center">
      <ul>
        <li v-for="possibleKey in possibleKeys" v-bind:key="possibleKey">{{possibleKey}}<br></li> 
      </ul>
      </v-row>
      <br><br>
      <hr>
      <br><br><u><h2 class ="">Select Key:</h2></u><br>
      <v-row justify="center">
        <template v-if="sharpsOrFlats == 'sharps'">
        <v-select
          @change="resetOnlyBtnsAndList()"
          v-model="selectedKey"
          :items="allNotesSharp"
          label="Root Note"
          outlined
          dense
        ></v-select>
        </template>
        <template v-else>
        <v-select
          @change="resetOnlyBtnsAndList()"
          v-model="selectedKey"
          :items="allNotesFlat"
          label="Root Note"
          class="select mr-3"
          outlined
          dense
        ></v-select>
        </template> 
        <v-select
          @change="resetOnlyBtnsAndList()"
          v-model="selectedType"
          :items="keyTypes"
          label="Type"
          class="select mr-3"
          outlined
          dense
          
        ></v-select>
        <v-btn @click="selectChords()">Submit</v-btn> 
        <template v-if="isAudible">
        <v-btn @click="playScale()">Play</v-btn>
        </template>
        </v-row><br>
        <v-row justify="center">
        <template v-if="selectedKey && selectedType && isSubmitted">
        <br><br><b><u>Key of {{selectedKey}} {{selectedType}}:</u>
        <template v-if="selectedType == 'Major' && currentChordList.length > 0">
         {{this.currentChordList.join(', ')}} <!-- display normally if it's a major key -->
         </template> 
        <template v-if="selectedType == 'Minor' && currentChordList.length > 0">
         {{this.currentChordList[5]}}, {{this.currentChordList[6]}}, {{this.currentChordList[0]}}, {{this.currentChordList[1]}}, {{this.currentChordList[2]}},
         {{this.currentChordList[3]}}, {{this.currentChordList[4]}}  <!-- displayed with root first if it's a minor key -->
         </template>
         </b>
         </template><br>
        </v-row>
       <br>
      <hr><br><br>
    <div row justify="center" class="settings" >
      <u><h2>Settings:</h2></u><br>
      <v-btn @click="reset();">Reset Chords</v-btn><br><br>
      <v-row justify="center">
      <v-radio-group row style="display: inline-block" v-model="activeRadio">
      <v-radio 
        name="activeRadio"
        key="0"
        label="Sharps"
        id="sharpsRadio"
        :value="0"
        @change="changeSharpsFlats()">
      </v-radio>
      <v-radio
        name="activeRadio"
        key="1"
        label="Flats"
        :value="1"
        id="flatsRadio"
        @change="changeSharpsFlats()">
      </v-radio>
      </v-radio-group>
      </v-row>
      <v-row justify="center">
      <v-switch v-model="isAudible" @change="changeSound()" :label="soundOnOff"></v-switch> 
      </v-row>
      <v-row justify="center">
      <v-switch v-model="isShowingTips" @change="disableTooltips()" :label="tooltipOnOff"></v-switch> 
      </v-row>
    </div>
    <v-sheet elevation="12" class="pa-12">
      <h4><u>Note:</u></h4>
      <br>Please simplify all specified chord types to their triad form, like so... <!-- TODO: add more chord buttons for other types. split the strings containing any of the minor 7s, major 7s, sus, etc. then just use that as major/minor in checkKeys() -->
      <br><br><i><b>Major </b> (1, 3, 5) &larr; Major 7 (maj7), Suspended (sus), Add (add), Dominant 7 (7)</i>
      <br><i><b>Minor </b> (1, b3, 5) &larr;  Minor 7 (m7), Minor 6 (m6) </i>
      <br><i><b>Diminished </b> (1, b3, b5) &larr; Half Diminished (m7b5), Fully Diminished(dim7)</i><br><br>
      </v-sheet><br><br>
  </div>
  </body>
  </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
    selectedKey: null,
    isSubmitted: false,
    selectedType: null,
    sharps: ['A#', 'C#', 'D#', 'F#', 'G#'],  // to be reassigned to sharpsFlats array
    flats: ['Bb', 'Db', 'Eb', 'Gb', 'Ab'], // to be reassigned to sharpsFlats array
    keyTypes: ['Major', 'Minor'],  // TODO: add harmonic minor and other exotic keys
    red: ['red--text'], // use to change text color on each button, signifiying if it's correct or not
    green: ['green--text'],
    soundOnOff: "Sound On",
    tooltipOnOff: "Tooltips On",
    isShowingTips: true,
    isAudible: true,
    sharpsOrFlats: "sharps",
    activeRadio: 0,
    sharpsFlats: ['A#', 'C#', 'D#', 'F#', 'G#'], // will be dynamically reassigned based on the radio button that is clicked
    currentChordList: [],
    possibleKeys: [],
    chordBtns : [ // defaulting to sharps and red buttons, but will be dynamically reassigned
      {chord: 'A', color: 'red--text', selected: false}, {chord: 'A#', color: 'red--text', selected: false}, {chord: 'B', color: 'red--text', selected: false}, {chord: 'C', color: 'red--text', selected: false}, {chord: 'C#', color: 'red--text', selected: false}, 
      {chord: 'D', color: 'red--text', selected: false}, {chord: 'D#', color: 'red--text', selected: false}, {chord: 'E', color: 'red--text', selected: false}, {chord: 'F', color: 'red--text', selected: false}, {chord: 'F#', color: 'red--text', selected: false},
      {chord: 'G', color: 'red--text', selected: false}, {chord: 'G#', color: 'red--text', selected: false},

      {chord: 'Am', color: 'red--text', selected: false}, {chord: 'A#m', color: 'red--text', selected: false}, {chord: 'Bm', color: 'red--text', selected: false}, {chord: 'Cm', color: 'red--text', selected: false}, {chord: 'C#m', color: 'red--text', selected: false}, 
      {chord: 'Dm', color: 'red--text', selected: false}, {chord: 'D#m', color: 'red--text', selected: false}, {chord: 'Em', color: 'red--text', selected: false}, {chord: 'Fm', color: 'red--text', selected: false}, {chord: 'F#m', color: 'red--text', selected: false},
      {chord: 'Gm', color: 'red--text', selected: false}, {chord: 'G#m', color: 'red--text', selected: false},

      {chord: 'Adim', color: 'red--text', selected: false}, {chord: 'A#dim', color: 'red--text', selected: false}, {chord: 'Bdim', color: 'red--text', selected: false}, {chord: 'Cdim', color: 'red--text', selected: false}, {chord: 'C#dim', color: 'red--text', selected: false}, 
      {chord: 'Ddim', color: 'red--text', selected: false}, {chord: 'D#dim', color: 'red--text', selected: false}, {chord: 'Edim', color: 'red--text', selected: false}, {chord: 'Fdim', color: 'red--text', selected: false}, {chord: 'F#dim', color: 'red--text', selected: false},
      {chord: 'Gdim', color: 'red--text', selected: false}, {chord: 'G#dim', color: 'red--text', selected: false}
    ],
    allNotesSharp: ['A', 'A#', 'B', 'C', 'C#', 'D', 'D#', 'E', 'F', 'F#', 'G', 'G#'],
    allNotesFlat: ['A', 'Bb', 'B', 'C', 'Db', 'D', 'Eb', 'E', 'F', 'Gb', 'G', 'Ab'],
    musicalKeys: {
      keyOfC:  ["C", "Dm", "Em", "F", "G", "Am", "Bdim"],
      KeyOfCsharp: ["C#", "D#m", "Fm", "F#", "G#", "A#m", "Cdim"],
      keyOfD:  ["D", "Em", "F#m", "G", "A", "Bm", "C#dim"],
      keyOfDsharp: ["D#", "Fm", "Gm", "G#", "A#", "Cm", "Ddim"],
      keyOfE: ["E", "F#m", "G#m", "A", "B", "C#m", "D#dim"],
      keyOfF:["F", "Gm", "Am", "A#", "C", "Dm", "Edim"],
      keyOfFsharp:["F#", "G#m", "A#m", "B", "C#", "D#m", "Fdim"],
      keyOfG: ["G", "Am", "Bm", "C", "D", "Em", "F#dim"],
      keyOfGsharp: ["G#", "A#m", "Cm", "C#", "D#", "Fm", "Gdim"],
      keyOfA: ["A", "Bm", "C#m", "D", "E", "F#m", "G#dim"],
      keyOfAsharp: ["A#", "Cm", "Dm", "D#", "F", "Gm", "Adim"],
      keyOfB: ["B", "C#m", "D#m", "E", "F#", "G#m", "A#dim"]
    }
  }},
    methods: {  
      changeSound() {
        if(this.soundOnOff == "Sound Off"){   //TODO: change sounds to be on/off here
          this.soundOnOff = "Sound On";
          this.isAudible = true;
        }
        else{
          this.soundOnOff = "Sound Off";
          this.isAudible = false;
        }
      },
      disableTooltips() {
        if(this.tooltipOnOff == "Tooltips Off" && this.isShowingTips == false){
          this.tooltipOnOff = "Tooltips On";
          this.isShowingTips = true;
        }
        else{
          this.tooltipOnOff = "Tooltips Off";
          this.isShowingTips = false;
        }
      },
      getColor(chord){   
        var result = this.chordBtns.find(obj => {return obj.chord === String(chord)})
        return result.color;
      },
      isSelected(chord){   
         var result = this.chordBtns.find(obj => {return obj.chord === String(chord)}); 
         return result.selected;
      },
      changeSharpsFlats() {
        if(this.sharpsOrFlats == "sharps"){
          // change all notes to flats
          this.sharpsOrFlats = "flats";
          this.sharpsFlats = this.flats;
          this.reformatLists();
        }
        else if(this.sharpsOrFlats == "flats"){
          // change all notes to sharps
          this.sharpsOrFlats = "sharps";
          this.sharpsFlats = this.sharps;
          this.reformatLists();
        }
      },
      playScale() {
        
         // TODO: play scale associated with key
        if(this.selectedKey && this.selectedType && this.isAudible){

            var note = this.selectedKey;

            if(note.includes("b")){
              var flatNote = note.substring(0,2);
              var restOfChord = note.substring(2);
              for(let j = 0; j < 5; j++){    // change all flats to sharps automatically, because mp3 files are only written in sharp
                  if(flatNote == this.flats[j]){
                      note = this.sharps[j] + restOfChord;
                  }
              }
            }
            if(note.includes("#"))
              note = note.replace("#", "sharp"); // change "#" to "sharp" because mp3 files do not have # character
            
            var filename = "sounds/scales/" + String(note) + String(this.selectedType) + ".mp3";
            var sound = new Audio(filename);
            sound.volume = 0.6;
            sound.play();
        }

      },
      playChord(chord){

        // technically could use an identifier and combine both playScale and playChord methods... lol

        if(this.isAudible && this.isSelected(chord)){ // play sound if switched ON and selecting a button (dont play sound when deselecting)

          if(chord.includes("b")){
            var flatNote = chord.substring(0,2);
            var restOfChord = chord.substring(2);
            for(let j = 0; j < 5; j++){    // change all flats to sharps automatically, because mp3 files are only written in sharp
                if(flatNote == this.flats[j]){
                    chord = this.sharps[j] + restOfChord;
                }
            }
          }
          if(chord.includes("#"))
            chord = chord.replace("#", "sharp"); // change "#" to "sharp" because mp3 files do not have # character

            var filename = "sounds/chords/" + String(chord) + ".mp3";
            var sound = new Audio(filename);
            sound.volume = 0.6;
            sound.play();
        }
      },
      reset(){
        this.selectedType = null;
        this.selectedKey = null;
        this.currentChordList = [];
        this.isSubmitted = false;
        this.possibleKeys = [];
        for (let i = 0; i < this.chordBtns.length; i++)   // reset all buttons back to red
            this.chordBtns[i].color = this.red;
      },
      reformatLists() {
        // reassign sharps/flats in currentChordList, chordBtns, possibleKeys as necessary

        var restOfChord, flatNote, sharpNote, x, y, keyOf, secondPart, ending = "";

        if(this.sharpsFlats == this.sharps){
          
            // changing flats to sharps

            // ...for all Notes --- WILL NOT WORK, CANNOT CHANGE DROPDOWN SELECTIONS DYNAMICALLY BY CHANGING THE ARRAY IT'S ASSOCIATED WITH
            /*for(let i of this.allNotes){
              if(i.includes("b")){
                for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                    if(i == this.flats[j]){
                        i = this.sharps[j];
                    }
                }
              }
            }*/

            // ...for all Keys
            Object.values(this.musicalKeys).forEach((keyToChange) => {
              for(let i = 0; i < keyToChange.length; i++){
                if(keyToChange[i].includes("b")){
                      flatNote = keyToChange[i].substring(0,2)
                      restOfChord = keyToChange[i].substring(2);
                      for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                        if(flatNote == this.flats[j]){
                          keyToChange[i] = this.sharps[j] + restOfChord;
                        }
                      }
                  }
              }
            });
            // ...for currentChordList
            if(this.currentChordList.length > 0){
              for(let i = 0; i < this.currentChordList.length; i++){
                if(this.currentChordList[i].includes("b")){
                    flatNote = this.currentChordList[i].substring(0,2)
                    restOfChord = this.currentChordList[i].substring(2);
                    for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                      if(flatNote == this.flats[j])
                        this.currentChordList[i] = this.sharps[j] + restOfChord;
                    }
                }
              }
            }
            // ... for chordBtns
            for(let i of this.chordBtns){
              flatNote = i.chord.substring(0,2)
              restOfChord = i.chord.substring(2);
              if(i.chord.includes("b")){
                  for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                    if(flatNote == this.flats[j]){
                       i.chord = this.sharps[j] + restOfChord;
                    }
                  }
              }
            }
            if(this.possibleKeys.length > 0){
              // ... for possibleKeys list
              for (let i = 0; i < this.possibleKeys.length; i++){
                
                  if(this.possibleKeys[i].includes("b")){
                      x = this.possibleKeys[i].split(' ')
                      keyOf = x.slice(0, 2).join(' ') // Key Of...
                      secondPart =  x.slice(2).join(' ');
                      y = secondPart.split(' ')
                      flatNote = y.slice(0, 1).join(' ')  // ...note on its own...
                      ending = y.slice(1, 2).join(' ') // ...minor or major
                    for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                        if(flatNote == this.flats[j])
                          this.possibleKeys[i] = keyOf + " " + this.sharps[j] + " " + ending;
                    }
                }
              }
            }
        }
        else if(this.sharpsFlats == this.flats){
          // change sharps to flats

            // ...for all Notes
            /*
            for(let i of this.allNotes){
              if(i.includes("#")){
                for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                    if(i == this.sharps[j]){
                        i = this.flats[j];
                        console.log('changed to ' + i)
                    }
                }
              }
            }*/

            // ...for all Keys
            Object.values(this.musicalKeys).forEach((keyToChange) => {
              for(let i = 0; i < keyToChange.length; i++){
                if(keyToChange[i].includes("#")){
                      sharpNote = keyToChange[i].substring(0,2)
                      restOfChord = keyToChange[i].substring(2);
                      for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                        if(sharpNote == this.sharps[j]){
                          keyToChange[i] = this.flats[j] + restOfChord;
                        }
                      }
                  }
              }
            });

            // ... for currentChordsList
            if(this.currentChordList.length > 0){
              for(let i = 0; i < this.currentChordList.length; i++){
                if(this.currentChordList[i].includes("#")){
                    sharpNote = this.currentChordList[i].substring(0,2);
                    restOfChord = this.currentChordList[i].substring(2);
                    for(let j = 0; j < 5; j++){  // run this 5 times because there are 5 sharps/flats
                      if(sharpNote == this.sharps[j]){
                        this.currentChordList[i] = this.flats[j] + restOfChord; // insert flat in place of the sharp note by using the index
                    }
                  }
                }
              }
            }
            // ... for chordBtns
            for(let i of this.chordBtns){
              if(i.chord.includes("#")){
                  sharpNote = i.chord.substring(0,2)
                  restOfChord = i.chord.substring(2);
                  for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                    if(sharpNote == this.sharps[j]){
                      i.chord = this.flats[j] + restOfChord;
                    }
                  }
              }
            }
            if(this.possibleKeys.length > 0){
              // ... for possibleKeys list
              for (let i = 0; i < this.possibleKeys.length; i++){

                  if(this.possibleKeys[i].includes("#")){
                      x = this.possibleKeys[i].split(' ')
                      keyOf = x.slice(0, 2).join(' ') // Key Of...
                      secondPart =  x.slice(2).join(' ');
                      y = secondPart.split(' ')
                      sharpNote = y.slice(0, 1).join(' ')  // ...note on its own...
                      ending = y.slice(1, 2).join(' ') // ...minor or major
                    for(let j = 0; j < 5; j++){ // run this 5 times because there are 5 sharps/flats
                        if(sharpNote == this.sharps[j])
                          this.possibleKeys[i] = keyOf + " " + this.flats[j] + " " + ending;
                    }
                }
              }
            }
        }
      },
      resetOnlyBtnsAndList(){
        // partial reset... will not be resetting selectedKey or selectedType
        this.currentChordList = [];
        this.possibleKeys = [];
        for (let i = 0; i < this.chordBtns.length; i++)   // reset all buttons back to red
            this.chordBtns[i].color = this.red;
      },
      selectChords(){

        this.resetOnlyBtnsAndList();

         if(this.selectedKey != null && this.selectedType != null){
            if(this.selectedType == "Major"){
                // if the key type is major, then use selectedKey to find the first chord (root) and  populate the buttons and chordList with that key list/array
                Object.values(this.musicalKeys).forEach((keyToCheck) => {
                  if(this.selectedKey == keyToCheck[0]){
                    for(let i of keyToCheck){
                       this.addToList(i);  // handles selecting, adding to chordList, changing color of buttons
                    }
                    this.checkKeys(); // to populate possibleKeys
                  }
                });
                this.isSubmitted = true;  // to handle v-if displaying name of key and its chords

            }
            else if(this.selectedType == "Minor"){
              Object.values(this.musicalKeys).forEach((keyToCheck) => {
                 // if the key type is minor, then use selectedKey to find the sixth chord (relative minor) and populate the buttons and chordList with that key list/array
                  var relativeMinorChord = this.selectedKey + "m"; // add "m" to the root of the minor key
                  if(keyToCheck[5] == relativeMinorChord){  // if the relative minor chord we submitted is the 6th chord of the key, then populate that key list/array
                    for(let i of keyToCheck){
                       this.addToList(i); // handles selecting, adding to chordList, changing color of buttons
                    }
                    this.checkKeys(); // to populate possibleKeys
                  }
                });
                this.isSubmitted = true;

            }
         }
         else {
           alert('Error: Please select a root note and key type before submitting.');
         }
         
      },
      addToList(chord) {
        this.isSubmitted = false; // remove Key Of x xxxx: [chordlist]... when changing the pre-selected key
        const errorMsg = "Error: Cannot select more than 7 chords. There are only 7 chords in a key!";
        var currChord = this.chordBtns.find(obj => {return obj.chord === String(chord)});  // contains currChord.chord, currChord.selected, currChord.color. grabs object associated with "chord" parameter
        if(currChord){
          if(currChord.color == this.green){
              if(this.currentChordList.length - 1 >= 0){
                currChord.selected = false; // deselecting button...
                currChord.color = this.red;   // ...making the button red...
                this.removeFromList(currChord.chord); // ...and removing the chord from the list
              }
              else
                alert(errorMsg);
          }
          else if(currChord.color == this.red){
            if(this.currentChordList.length + 1 <= 7){
              currChord.selected = true; // selecting button...
              currChord.color = this.green;  // ...making the button green...
              this.currentChordList.push(currChord.chord);  // ...and adding chord to the list
            }
            else
              alert(errorMsg);
          }
        }
      },
      removeFromList(chord){
        this.isSubmitted = false;
        if(this.currentChordList.length > 0){
          // removing like this cuz there no built-in for removing an element from array by value :(
          var index = this.currentChordList.indexOf(chord);  
          if (index !== -1) 
            this.currentChordList.splice(index, 1);           // makes me appreciate python! 
        }
      },
      existsInKey(keyList, chordList){
        
        var matchCounter = 0;

        // checking if current chord list is a subset of the key
            for (let chord of chordList){
              for (let i = 0; i < keyList.length; i++){
                  if(keyList[i] == chord){
                    matchCounter++;
                  }
              } 
            }

        return matchCounter == chordList.length ? true : false;

      },
      checkKeys() {  

            if(this.currentChordList.length > 0 && this.currentChordList.length <= 7){

              this.possibleKeys = []

              Object.values(this.musicalKeys).forEach((keyToCheck) => {
                  if(this.existsInKey(keyToCheck, this.currentChordList)){
                      var rootNote = keyToCheck[0]; // will always be a major chord, so no need to splice here
                      var relativeMinorNote = keyToCheck[5].replace("m", ""); // automatically add the relative minor keys, cuz they contain the same chords just ordered differently
                      var majorKey = "Key of " + rootNote + " Major";
                      var minorKey = "Key of " + relativeMinorNote + " Minor";
                      this.possibleKeys.push(majorKey);
                      this.possibleKeys.push(minorKey);
                    }
              });
          }
          else if(this.currentChordList.length == 0)
              this.possibleKeys = [];
          
          }
      }
}
</script>
<style scoped>
h1, h2, h3, h4 {
  text-align: center;
  color: black;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  text-align: center;
    font-weight:bold;
}
.chords{
  display: grid;
  grid-template-columns: repeat(6, 1fr);  
  grid-auto-rows: minmax(50px, auto);
} 
.v-btn {
  text-transform: none !important;
}
.settings {
  text-align: center;
}
</style> <!-- TODO: change grid to one row of 12 for all notes. or two rows of 6? -->
