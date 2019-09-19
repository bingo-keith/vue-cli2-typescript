<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ author }}</h2>
    <button @click="handleClick">按钮</button>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import { Getter, Mutation } from 'vuex-class'

@Component
export default class HelloWorld extends Vue {
  @Getter author;
  @Mutation SET_AUTHOR;

  msg: String = 'hello world!'

  mounted () {
    console.log(this.author)
    this.changeAuthor('帅锅')
    console.log(this.author)
  }

  changeAuthor (name) {
    this.SET_AUTHOR(name)
  }

  handleClick () {
    console.log(this.author)
  }
}
</script>

<style lang="scss" scoped>
.hello {
  font-size: 20px;
  h1 {
    color: red;
  }
  h2 {
    color: blue;
  }
}
</style>
