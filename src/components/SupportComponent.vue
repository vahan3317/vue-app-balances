<template>
<div>
 <div class=" center  w-[327px] lg:w-[257px] h-[152px] border-2 rounded-[20.28px]   shadow-lg" v-for="support of supports" :key="support.title">
     <div class="flex mt-[27.02px] pl-[24px]">
            <div><img src="../assets/imgs/line.svg" alt=""></div>
      <div class="pt-[27.02px] pl-[32.14px]" >
          <p class="text-[23.61px] text-[#6E6E6E]">{{support.title}}</p>
            <div>
              <div class="flex mb-[35px]">
                
                <div class="text-[53.21px] ">{{support.inwork_count}}</div>
                  <div class="flex  flex-col ">
                    <p class="text-[24.43px]  pt-[8px] ">{{support.burning_count}}</p>
                    <img src="../assets/imgs/fire.svg" alt="" class="w-[11px] h-[15.15px] mb-[33.72px] ">
                  </div> 
                <div class="mt-[10.35px] pt-[7.35px] ">
                <div class="w-[109px] bg-gray-200 h-1 pl-[px] ">
                    <div class="w-[{{ support.progress }}%] bg-[#EFEFEF] rounded-lg "> <div class="w-[{{ support.progress }}%]  rounded-lg h-1 w-[75%] h-[16.69px]" ></div></div>
                    </div>
                  <div class="pt-[11px] lg:pt-[20px] lg:pl-[28.24px]">{{support.time_fakt}}</div>  
                </div>
              </div>  

            </div>
      </div>
      </div>
       
     
     </div>
</div>

</template>