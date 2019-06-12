<template>
  <div class="wrapper">
      <div class="start">
          <button id="start_btn" class="start_btn" v-show="start1" @click="start">{{message}}</button>
      </div>
      <div class="plate_con" v-show="dispaly" >
          <div class="plate pa">
              <app-plate v-for="item in items" :key="item"></app-plate>
          </div>
          <div class="plate pb" >
              <app-plate v-for="item in list" :key="item"></app-plate>
          </div>
          <div class="plate pc">
              <app-plate v-for="item in lists" :key="item"></app-plate>
          </div>
      </div>
  </div>
</template>

<script>
import Plate from './Plate'

export default {
  props: {
  },
  data () {
    return {
        message:"开始游戏",
        endmeg:"再来一局",
        items:[1,2,3],
        list:[1,2,3,4,5],
        lists:[1,2,3,4,5,6,7],
        dispaly:false ,
        start1:true ,   
    }
  },
  created () {},
  mounted () {
      this.remov();
     
  },
  watch: {},
  computed: {},
  methods: {
      start:function(){
          this.start1 = this.dispaly;
          this.dispaly = !this.start1;
        //   $(".start_btn").hide();
        //   $(".plate_con").show(); 

      },
      remov(){

            var self = this;
            var items = self.items;
            var list = self.list;
            var lists = self.lists;
            
          $(".item").click(function(){
              var count1 = $(this).parents(".pa").children();
              var count2 = $(this).parents(".pb").children();
              var count3 = $(this).parents(".pc").children();

              if(items.length == count1.length) {
                 items.pop();
                 var num1 = items.length;  
                           
              }
              if(list.length == count2.length){
                 list.pop();
                 var num2 = list.length;
                
              }
               if(lists.length == count3.length){
                 lists.pop();
                 var num3 = lists.length;
                  
              }
                var sum = num1 + num2 + num3;
                if(sum == 0){
                    alert("你输了!");
                }
          })          
      }
  },
  components: {
      "app-plate":Plate
  },
}
</script>
<style scoped>

.start{
    position: absolute;
    left: 0;
    right: 0;
    top: 45%;
    widows: 100%;  
    padding: 0 100px;
}

.start .start_btn{
    width: 100%;
    background-color: #63435e;
    line-height: 40px;
    border: none;
    color: white;
    border-radius: 5px;
    outline: none
}

.plate_con{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 50px 20px 0 20px;
    display: flex;
    display: -webkit-flex;
    flex-direction: column;
    justify-content: center;
}

.plate_con .plate{
    width: 100;
    display: flex;
    display: -webkit-flex;
    justify-content: center;
    padding: 20px 0;    
}

</style>