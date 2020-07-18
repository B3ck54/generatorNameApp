<template>
  <v-container>
    <v-row
    align="center">
      <v-col
      cols="12"
      class="text-center">
      <h1>Générateur de nom aléatoire</h1>
      </v-col>
    </v-row>
  <v-row>
    <v-col
    cols="6"
    class="text-center">
    <p>{{ name }}</p>
    </v-col>
  </v-row>
  <v-row>
    <v-col
    cols="6"
    class="text-center">        
    <v-btn 
    @click="generatorName">
    Générer
    </v-btn>
    </v-col>
  </v-row>
  <v-row>
  <v-col
  cols="6"
  class="text-center">        
  <v-btn
    @click="reset">

  Reset
  </v-btn>
  </v-col>
  </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
        name: '',
        arrayAlphabet : ['AI','BA','CI','DU','EN','FA','GO','AH','PI','JO','KO','LE','MI','NY','RO','PA','QUI','RA','S','T','U','V','W','X','Y','Z'],
    }),
      methods: {
      generatorName: function () {
        while (this.name.length < 6) {
        this.name += this.arrayAlphabet[Math.floor(Math.random() * this.arrayAlphabet.length)];
        return this.name
        } 
      },
      reset: function(){
         Object.assign(this.$data, this.$options.data());
      }
    }
  }
</script>
