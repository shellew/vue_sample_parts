<template>
  <div id="app">
    <input type="text" v-model="textInput">
    <p>{{ textInput }}</p>
  </div>

  <div class="input-form">
    <form novalidate class="ui form" @submit.prevent="onSubmit">
      <div class="field">
        <input v-model="newItem" type="text" placeholder="Add an item!">
      </div>
      <button type="submit" class="ui button">送信</button>
    </form>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "SampleInput",
  setup() {
    const newItem = ref<String>('')
    const onSubmit = () => {
      console.log('New Item:', newItem.value);
    }
    return {
      onSubmit,
      newItem
    }
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
}
a {
  color: #42b983;
}
</style>
