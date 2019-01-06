<template>
  <div class="hello">
    <textarea v-model="noviTekst" id="textBox">

    </textarea>
    <button v-on:click="dodaj" id="dugme">Dodaj</button>

    <ul>
      <li v-for="biljeska in nizTekst" :key="biljeska.id">{{ biljeska }}
        <button v-on:click="izbrisi(biljeska)" id="dugmeIzbrisi"> X </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      noviTekst: '',
      nizTekst: [],
    };
  },
  methods: {
    dodaj() {
       this.nizTekst.push(this.noviTekst);
   },
    izbrisi(biljeska) {
      this.nizTekst.splice(this.nizTekst.indexOf(biljeska),1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  width:30%;
  border: 3px solid black;
  margin-top: 7px;
  height:auto;
  background:darkblue;
  border-radius: 9px;
  color:white;
}
a {
  color: #42b983;
}
#dugme {
  border:2px solid darkblue;
  border-radius: 22px;
  height:50px;
  width:100px;
  margin-left:5px;
  position:absolute;
  top:125px;
  color:white;
  background: darkblue;
  outline: none;
}
#textBox {
  resize: none;
  height:160px;
  width:500px;
  border: 3px solid darkblue;
  border-radius: 33px;
  outline: none;
  padding:20px;
  font-size: 20px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  padding:10px;
}
#dugmeIzbrisi {
  float:right;
  color:crimson;
  border-radius: 9px;
}
</style>
