<template>
 <div class="font-['Cera_Pro']   " >
    <p class="text-center  font-[500] py-[72.29px] text-[24px] font-['Cera_Pro'] leading-[47.21px] lg:flex  ">Проекты поддержки</p>

<div class="mt-[20px] lg:grid lg:grid-cols-3 lg:gap-[18px] cursor-pointer  2xl:flex 2xl:mb-[18px] lg:mb-[18px]  " v-show="dontshow">   

    <div class=" center  w-[327px] lg:w-[257px] h-[152px] border-2 rounded-[20.28px]   shadow-lg" v-for="support of supports" :key="support.title">
     <div class="flex mt-[27.02px] pl-[24px]">
            <div><img src="../assets/imgs/line.svg" alt=""></div>
      <div class=" pl-[20.28px]" >
          <p class="text-[23.61px] text-[#6E6E6E]">{{support.title}}</p>
            <div>
              <div class="flex mb-[35px]">
                
                <div class="text-[53.21px] ">{{support.inwork_count}}</div>
                  <div class="flex  flex-col ">
                    <p class="text-[24.43px]  pt-[10px] pl-[5.91px] money ">{{support.burning_count}}</p>
                    <img src="../assets/imgs/fire.svg" alt="" class="w-[11px] h-[15.15px] mb-[33.72px] ml-[5.91px] ">
                  </div> 
                <div class="mt-[10.35px] pt-[7.35px] ">
                <div class="w-[109px] bg-gray-200 h-1 ml-[13.65px]  ">
                    <div class="w-[100%] bg-[#EFEFEF] rounded-lg "> <div class="bg-[#39B8BA] rounded-lg h-1 w-[{{ support.progress }}] h-[16.69px]" ></div></div>
                    </div>
                  <div class="pt-[11px] lg:pt-[20px]  pl-[16px]">{{support.time_fakt}}</div>  
                </div>
              </div>  

            </div>
      </div>
      </div>
       
     
     </div>
</div>

<div class=" flex-row lg:grid lg:grid-cols-3 lg:gap-[18px] cursor-pointer mb-[46px]  2xl:flex lg:mb-[72.29px] 2xl:mb-[50px] ">   

    <div class=" center w-[327px] lg:w-[257px] h-[152px] border-2 rounded-[20.28px] hover:bg-gray-100    shadow-lg" v-for="support of supports" :key="support.title">
          <div  class="flex mt-[27.02px] pl-[24px]">
            <div><img src="../assets/imgs/line.svg" alt=""></div>
            <div class="    pl-[20.28px] ">
              <p class="text-[23.61px] text-[#6E6E6E]">{{support.title}}</p>
                <div>
                  <div class="flex mb-[35px]">
                    
                      <div class="text-[53.21px] ">{{support.inwork_count}}</div>
                            <div class="flex  flex-col ">
                                <p id="money" class="text-[24.43px] money  pt-[10px] ">{{support.burning_count}}</p>
                                <img src="../assets/imgs/fire.svg" alt="" class="w-[11px] h-[15.15px]  ">
                            </div> 
                            <div class="mt-[10.35px] pt-[7.35px] ">
                                <div class="w-[109px] bg-gray-200 h-1 ml-[13.65px]">
                                <div class="w-[{{ support.progress }}%] bg-[#EFEFEF] rounded-xl"> <div class="bg-[#39B8BA] rounded-lg h-1 w-[{{ support.progress }}%] h-[16.69px]" ></div></div>
                          </div>
                        <div class="pt-[11px] lg:pt-[21px] pl-[16px]">{{support.time_fakt}}</div>  
                      </div>
                  </div>  

            </div>
            </div>
  </div>
    </div>
   

</div>
<button class="w-[323px] h-[53.7px] bg-[#39B8BA] hover:bg-[#3e9c9e] rounded-[23.61px] text-white lg:w-[221.21px] lg:mt-[72.29px] lg:mb-[72.29px] 2xl:mt-[72.29px]  " style="display:block; margin: 0 auto;margin-top: 72.29px;margin-bottom: 72.29px;" @click="dontshow = !dontshow" v-show="!dontshow">Показать еще</button>
   <button class="w-[323px] h-[53.7px] bg-[#39B8BA] hover:bg-[#3e9c9e] rounded-[23.61px] text-white lg:w-[221.21px] lg:mb-[72.29px]   " style="display:block; margin: 0 auto;"  @click="dontshow = !dontshow" v-show="dontshow">Показать менше</button>
      

 </div>
</template>
<script>
import axios from 'axios';
export default {
name:"support",
data(){
 return{
   supports:[],
    dontshow:false
   // support:[]
 }
},

async created(){
 try{

  const result = await axios.get(` http://localhost:3000/supports`);
  this.supports = result.data
  
  
  
 }catch(e){
  console.error(e)
 }
},
methods:{
 async alo(){
    await alert('hello')
 }
}
}
</script>
<style>

.money{
  color:red;
}

</style>
