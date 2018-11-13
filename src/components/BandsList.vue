<template>
  <div>
    <input type="text" placeholder="Add Band" 
    @keyup.enter="addBand"   
     v-model="newBand">
    <button @click="addBand" >Add</button>

  <ul>
    <BandItem v-for="band in bands" :key="band" :thisBand="band">
    </BandItem>
  </ul>

  </div>
</template>
<script>
import BandItem from '@/components/BandItem.vue';

export default {
  name:'BandsList',
  newBand:'',
  currentId:2,
  components:{
    BandItem
  },
  data(){
    return{
bands:[{
  id:1,
  name: 'ColdPlay',
  songs:['Yellow','Fix you','Mylo xylot']
},
{
  id:2,
  name: 'Metallica',
  songs:['Iron Man']
}

]
    }
  },
   methods:{
addBand(){ 
  this.currentId++;
  this.bands.push({
  id:this.currentId,
  name:this.newBand,
  songs:[]
});
}
  }

}
</script>
