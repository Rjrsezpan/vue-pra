<template>
  <div class="view">
    <h1 class="title">{{title}}</h1>
    <input type="text" v-model='newStr' @keyup.enter='addItem'/>
    <ul>
      <li v-for="item in items" v-bind:class="{finish:item.isFinished}" @click="toggleFinish(item)">
        {{item.text}}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "list",
    data() {
      return {
        title: 'TO DO LIST',
        items: [],
        newStr: ''
      }
    },
    methods: {
      toggleFinish: function (item) {
        item.isFinished = !item.isFinished;
      },
      addItem: function () {
        this.items.push({
          text: this.newStr,
          isFinished: false
        })
        //自訂義事件，並傳遞參數
        this.$emit('myMsg', this.newStr);
        this.newStr = ''
      }
    }
  }
</script>

<style scoped>
  .view {
    width: 400px;
    border: 1px solid gray;
    margin: 20px auto;
  }

  .view .title {
    border-bottom: 1px solid gray;
  }

  .view ul li {
    margin: 10px 0px;
    list-style: none;
  }

  .view .finish {
    color: gray;
    text-decoration: line-through;
  }
</style>
