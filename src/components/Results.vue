<template>
  <p>Reaction Time : {{score}} ms </p>
  <p>{{rank}}</p>
</template>

<script>
export default {

    props:['score'],

    data() {
        return {
            rank:null
        }

    },

    mounted() {

        if(this.score<250)
        this.rank="INHUMAN"
        else if (this.score<400)
        this.rank="PRETTY GOOD"
        else if (this.score<600)
        this.rank="You can do better."
        else
        this.rank="We can not be good at everything right ?"
    }





}
</script>

<style>
  .rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
  }
</style>