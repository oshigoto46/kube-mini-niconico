<template>
    <div>
        <div>test: {{ test }}</div>
        <div>test2: {{ test2 }}</div>
        <div>test2: {{ test3 }}</div>
        <div>test2: {{ test4 }}</div>
        <div>test2: {{ hoges }}</div>
    </div>
</template>

<script>
export default {
    async asyncData({app}) {
      const res = await app.$axios.get('/hoge')
        return {
            hoges: "hoge" ,// res.data,
            test: "asyncData",
            test2: "asyncData2",
            test3: "asyncData3"
        };
    },
    data() {
        return {
            test: "data",
            test2: "data2",
            test4: "data4",
            hoges : []
        };
    },
};
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
