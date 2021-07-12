<template>
  <div id = "app">
  "hoge"
  {{message}}
  </div>
</template>

<script>
export default {
  props: {
    data: {
　   　message: 'Hello World'
　  }
  }
}
</script>

<style>
.name {
  font-size: 16px;
  font-weight: bold;
}
.created-at {
  color: gray;
}
.content {
  margin: 0px;
  font-size: 16px;
  white-space: pre-line;
}
</style>
