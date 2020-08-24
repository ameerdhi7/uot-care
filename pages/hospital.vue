<template>
  <h1>{{hospitalId}}</h1>
</template>
<script>
  export default {
    name:'hospital',
    props: {
      hospitalId: {type:String,required:true}
    }
  }
</script>
