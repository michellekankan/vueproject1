<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  created() {
    const api = `${process.env.APIPATH}/api/${process.env.CUSTOMPATH}/products`;
    //API伺服器路徑
    //所申請的APIPATH
    console.log(process.env.APIPATH, process.env.CUSTOMPATH);
    this.$http.get(api).then((res) => {
      console.log(res.data)
    })
    
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

</style>
