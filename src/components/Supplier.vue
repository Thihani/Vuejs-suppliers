

<template>
<div id="suppliers">
    <h1 > {{name}}</h1>
    <h3 v-if="status" style="color:#41b883">Have stock? Yes</h3>
    <h3 v-if="!status" style="color:red">Have stock? No</h3>
    <h5> Stock checked at: {{format(checkedAt)}}</h5>  
</div>
</template>

<script>

import {format} from 'timeago.js';
export default {
  name: "Supplier",
  props: {
    name: String,
    status: Boolean,
    checkAt: String
  },
  methods:{
    format
  }
}
</script>

<style>
#suppliers{
  border:1px solid black;
  margin-bottom:10px;
  margin-left: 200px;
  margin-right: 200px;
}
</style>