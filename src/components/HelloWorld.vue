<template>
  <div class='hellobox'>
    <pre class="b1">
    {{msg}}
    </pre>
    <div class="b2">
      <textarea rows="4" cols="50" v-model="txt" v-on:keyup.enter="onEnter">
        At w3schools.com you will learn how to make a website. We offer free tutorials in all web development technologies.
      </textarea>
      <input type="submit" value="Submit" v-on:click="submit" >
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '',
      txt: ''
    }
  },
  methods: {
    submit: function (bCallFromOnEnter) {
      var bFlag = false
      bFlag = bCallFromOnEnter
      this.msg += this.txt
      this.txt = ''
    },
    onEnter: function () {
      this.submit(true)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hellobox{
  height: 100%;
}

.b1{
  background-color:#FFD382;
  height: 80%;
}

.b2{
  background-color:rgb(130, 205, 255);
  height: 20%;
}

</style>
