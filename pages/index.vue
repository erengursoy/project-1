<template>
<div>
  <h2>Frameworkler</h2>
  <ul>
    <li v-for="framwork in framworks" :key="framwork" class="list" :class="{selected:framwork.selected}" @click="selectTag(framwork)">
{{framwork.name}}
    </li>
  </ul>
  <h3>Seçilen Frameworkler</h3>
  <ul>
    <li v-for="s in  selectedTags" :key="s">
{{s.name}}
    </li>
  </ul>
</div>
</template>

<script>
export default {
  data(){
    return{
      framworks:[
         {
          name:"vue",
          selected:true
          
         },
         {
          name:"react",
          selected:false
          
         },
         {
          name:"svelte",
          selected:false
          
         },
          {
          name:"angular",
          selected:false
          
         },
         

      ]
    }
  },
  methods:{
selectTag(framwork){
  framwork.selected= !framwork.selected
  
      }
  },
  computed:{
    selectedTags(){
      console.log("değişiklik oldu")
      return this.framworks.filter(i=>i.selected)
    }
  }
}
</script>
<style scoped>
.list{
  list-style-type: none;
  background: #131415;
  color: #a1b2c3;
  margin: 20px;
  padding: 10px 20px;
  border-radius: 15px;
  align-items: center;
  display: inline-block;
  cursor: pointer;
}
.list.selected{
  background: #714131;

}
.button{
  border-radius: 15px;
  background-color: #0a6540;
  color: #a1b2c3;
  padding: 10px 20px;
}
</style>