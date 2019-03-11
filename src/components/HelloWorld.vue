<template>
  <div class="hello">
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
<style scoped>

</style>
