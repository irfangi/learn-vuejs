<template>
  <div class="main">
    <div class="container">
      <h4>Doc</h4>
      <p>
        v-bind:key shorthand(:key) exp: :id :[idkey] <br />
        v-on:[key] shorthand(@event) exp: @click @[event]
      </p>
      <hr />
      <!-- output html -->
      <h4>
        {{ title }}
      </h4>

      <!-- component with for and send param string and method -->
      <List
        v-for="(list, index) in lists"
        v-bind:key="index"
        :test="list"
        :method="() => listClicked()"
      />
      <!-- output html view string -->
      <p v-html="htmlText"></p>
      <!-- dinamic argument -->
      <p :[dinamicArgument]="content">{{ content }}</p>
      <!-- event listener -->
      <button @click="helloWord">
        Clickme
      </button>
      <!-- watcher -->
      <input type="text" v-model="question" placeholder="watcher" />

      <div class="list-content">
        <p :class="{ 'class-color': true, 'class-underlane': classCondition }">
          Class
        </p>
        <p :style="{ color: 'red', 'text-decoration': 'underline' }">
          <span :style="[{ color: 'black' }]">ssss</span>
          <!-- can be multipel value {key:[wbkit,flex dll]} -->
          Style
        </p>
      </div>

      <div class="list-content">
        <h4>Conditional Rendering</h4>
        <p>v-if</p>
        <p v-if="condition1">Condition1</p>
        <p>v-else</p>
        <p v-if="condition2">Condition1</p>
        <p v-else>Condition2</p>
        <p>v-else-if</p>
        <p v-if="condition2">Condition2</p>
        <p v-else-if="condition1">Condition1</p>
        <p v-show="condition1">v-show</p>
        <p v-show="condition2">v-show not show</p>
        <!-- v-if using key was was good -->
        <p v-if="condition1" key="condition">IF with key Recomended</p>
      </div>
      <div class="list-content">
        <h4>List Rendering</h4>
        <p>List Array Object</p>
        <ul>
          <li v-for="(list, idx) in listArrayObject" :key="idx">
            {{ list.value }} - index : {{ idx }}
          </li>
        </ul>
        <ul>
          <li>Test using object bellow</li>
          <li v-for="({ value }, idx) in listArrayObject" :key="idx">
            {{ value }} - index : {{ idx }}
          </li>
        </ul>
        <p>List Object</p>
        <ul>
          <li v-for="(value, key) in listObject" :key="key">
            {{ value }} key : {{ key }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import List from "../components/List";

export default {
  name: "Home",
  components: {
    List,
  },
  mounted() {
    // console.log();
  },
  watch: {
    question: function(newQuestion) {
      console.log(newQuestion);
    },
  },
  methods: {
    listClicked: function() {
      console.log("clicked");
    },
    helloWord: function() {
      console.log("hello word");
    },
  },
  data: function() {
    return {
      question: "",
      title: "title",
      dinamicArgument: "id",
      lists: [1, 2, 3, 4, 5],
      htmlText: `<b style="color:'red'">Text<b>`,
      content: "content1",
      classCondition: true,
      condition1: true,
      condition2: false,
      listObject: {
        value1: 1,
        value2: 2,
        value3: 3,
      },
      listArrayObject: [{ value: 1 }, { value: 2 }, { value: 3 }],
    };
  },
};
</script>
<style scoped>
.class-color {
  color: aqua;
}
.class-underlane {
  text-decoration: underline;
}
</style>
