<template>
  <p class="reaction-time">Reaction Time : {{score}} ms </p>
  <p class="rank">{{rank}}</p>
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
    font-size: 2em;
    color: #0f5aaf;
    font-weight: bold;
  }

  .reaction-time{
      font-weight: bold;
  }
</style>