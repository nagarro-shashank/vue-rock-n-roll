<template>
  <li @click="toggle">
    {{thisBand.name}}
    <p v-show="open">
      {{thisBand.songs | join}}
      <input type="text" placeholder="Add song" 
      @click.stop 
      @keyup.enter="addSong"
      v-model="song"/>
    </p>
    </li>
</template>
<script>
export default {
  name:'BandItem',
  data(){
    return{
    open:false,
    song:''
    }
  },
  props:{
    thisBand:Object
  },
  filters:{
    join(arr){
      return arr.join(', ')
    }
  },
  methods:{
    toggle(){
      this.open=!this.open
    },
addSong(){
this.thisBand.songs.push(this.song);
}
  }
  
}
</script>

