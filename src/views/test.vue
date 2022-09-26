<template>

  <h1>Number of item {{notes.length}}</h1>
  <div class="list-group">
    <li class="list-group-item d-flex align-items-cente col-sm-4 shadow-sm justify-content-between align-items-center"  
    v-for="note in notes" :key="note.text"
    >
        <span> {{note.text}}</span>
        <span class="badge badge-pill">
            <button class="btn btn-danger"  @click="removeCar(note)">X</button>
        </span>
        <span class="badge badge-pill">
           <div>
                <input type="checkbox" :checked="note.isDone"/> 
           </div>
        </span>
    </li>
   </div>
   <div class="mb-3 col-sm-4">
    <label for="" class="form-label">Add Car</label>
    <input type="text" v-model="item" @keypress.enter ="addItem" 
    class="form-control shadow-sm" name="" id="" aria-describedby="helpId" placeholder="Add car">
    <small id="helpId" class="form-text text-muted"></small>
</div>
<button type="submit" class="btn btn-primary" @click="addItem">Add item #{{this.notes.length +1}}</button>


</template>

<script>
export default {

name:'my-first',
data()
{
    return{
        title:'Azad', 
        item:'',
        notes:[
            {text:'Item1', isDone:true},
            {text:'Item2', isDone:false},
            {text:'Item3', isDone:false},
            {text:'Item4', isDone:true},
        ]
    }
}, 
methods:{
    addItem()
    {
        if(this.item.length!==0)
        {
            this.notes.push({
            text : this.item,
            isDone :false
         });
         this.item =''

        }
    }, 
    removeCar(val)
    {
        this.notes = this.notes.filter(function(item) {
               return item.text !== val.text
        })
    },
}, 
computed:{
        itemsInList (){
              return this.notes.length
        }
       
    }

}
</script>

<style>

</style>