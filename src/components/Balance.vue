<template>
 <div class="font-['Cera_Pro']  " >
    <p class="text-center  font-[500] py-[72.29px] text-[24px] font-['Cera_Pro'] leading-[47.21px] lg:flex 2xl:text-[26px] ">Информация о балансах</p>

<div class="lg:grid lg:grid-cols-3 lg:gap-[18px] cursor-pointer  2xl:flex " >   

    <div class=" center mb-[24px] w-[327px] lg:w-[257px] h-[152px] border-2 rounded-[20.28px] hover:bg-gray-100    shadow-lg" v-for="balance of balances" :key="balance.title">
     <div class="pt-[35.43px]   ">
       <div class="font-bold pl-[20.28px] text-[23.61px] text-[#6E6E6E]  ">{{ balance.title }}</div>
            <p  class="text-gray-700 font-['Cera_Pro']  flex pl-[20.28px] text-[38.36px] lg:text-[40.56px] text-[#39B8BA]  ">
                  {{ balance.sum }} ₽
              <span v-show="balance.sum_plan!==null" class=" font-['Cera_Pro'] lg:text-[18.61px] text-gray-500 lg:pt-[18px] ">/{{ balance.sum_plan }} ₽</span>
            </p> 

            
        </div>
       
     
     </div>
   

</div>
<div class="  lg:grid lg:grid-cols-3 lg:gap-[18px] cursor-pointer  2xl:flex " v-show="!dontshow">   

    <div class=" center mb-[24px] w-[327px] lg:w-[257px] h-[152px] border-2 rounded-[20.28px] hover:bg-gray-100    shadow-lg" v-for="balance of balances" :key="balance.title">
     <div class="pt-[35.43px]   ">
       <div class="font-bold pl-[20.28px] text-[23.61px] text-[#6E6E6E]  ">{{ balance.title }}</div>
           <p class="text-gray-700 font-['Cera_Pro']  flex pl-[20.28px] text-[38.36px] lg:text-[40.56px] text-[#39B8BA]  ">
                  {{ balance.sum }} ₽
            <span v-show="balance.sum_plan!==null" class=" font-['Cera_Pro'] lg:text-[18.61px] text-gray-500 lg:pt-[18px] ">/{{ balance.sum_plan }} ₽</span>
          </p> 

            
        </div>
       
     
     </div>
   

</div>


<button class="w-[323px] h-[53.7px] bg-[#39B8BA] hover:bg-[#3e9c9e] rounded-[23.61px] text-white lg:w-[221.21px]      " style="display:block; margin: 0 auto;margin-top: 72.29px;margin-bottom: 72.29px;" @click="dontshow = !dontshow" v-show="dontshow">Показать еще</button>
   <button class="w-[323px] h-[53.7px] bg-[#39B8BA]  hover:bg-[#3e9c9e] rounded-[23.61px] text-white lg:w-[221.21px]   " style="display:block; margin: 0 auto; margin-top: 72.29px;margin-bottom: 72.29px;"  @click="dontshow = !dontshow" v-show="!dontshow">Показать менше</button>
      
<Support />
 </div>
</template>
<script>
import axios from 'axios';
import Support from './Support.vue';
export default {
    name: "balance",
    data() {
        return {
            balances: [],
            dontshow: true
            // support:[]
        };
    },
    mounted() {
    },
    async created() {
        try {
            const result = await axios.get(` http://localhost:3000/balances`);
            this.balances = result.data;
        }
        catch (e) {
            console.error(e);
        }
    },
    methods: {
        async alo() {
        }
    },
    components: { Support }
}
</script>
<style>



</style>
