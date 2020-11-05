<template>
  <view class="container">
    <StatusBar color="#1f1f1f" />
    <text class="container__title">To-Do App</text>
    <Todo />
  </view>
</template>

<script>
import StatusBar from './components/StatusBar'
import Todo from './components/Todo'

export default {
  components: {
    StatusBar,
    Todo
  }
}
</script>

<style>
  .container {
    background-color: #131313;
    height: 100%;
  }
  .container__title {
    font-size: 35px;
    color: #FFF;
    text-align: center;
    padding: 30px;
    font-weight: 900;
    background-color: #1f1f1f;
  }
</style>
