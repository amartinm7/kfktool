<template>
  <div class="hello">
    <div class="grid-container">
      <div class="grid-item"> hi </div>
      <div class="grid-item"> hello</div>
      <div class="grid-item"> world</div>
      <div class="grid-item"> say</div>
      <div class="grid-item"> hello</div>
      <div class="grid-item"> say</div>
      <div class="grid-item-1to2"> hello</div>
    </div>
    <ul v-for="item in groceryList" v-bind:key="item.id">
      <li> {{item.text}}</li>
    </ul>
  </div>
</template>

<script>

import kafka from 'kafka-node'


export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      kafkaConfig: {
        kafkaHost: '127.0.0.1:9092',

      },
      groceryList: [
        { id: 0, text: 'Vegetables' },
        { id: 1, text: 'Cheese' },
        { id: 2, text: 'Whatever else humans are supposed to eat' }
      ]
    }
  },
  methods: {
    readMessages: function() {
      const client = new kafka.KafkaClient();

    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

  .grid-container {
    display: grid;
    grid-column-gap: 0.5em;
    grid-row-gap: 0.5em;
    background-color: coral;
    grid-template-columns: auto auto auto;
    grid-template-rows: 10em auto;
    align-content: center;
  }

  .grid-item{
    border: 1em solid cadetblue;
    text-align: center;
  }

  .grid-item-1to2{
    border: 1em solid darkgoldenrod;
    grid-column-start: 1;
    grid-column-end: 3;
  }

</style>
