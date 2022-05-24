<template>
  <div class="font-inter">
    <div class="flex items-center justify-center h-full">
      <button class="py-2 px-4 bg-blue-500 text-white rounded hover:bg-blue-700" @click="toggleModal">Cancel Request</button>
    </div>
    <div class="fixed z-10 overflow-y-auto top-0 w-full left-0 hidden" id="modal">
      <div class="flex items-center justify-center min-height-100vh pt-4 px-4 pb-20 text-center sm:block sm:p-0">
        <div class="fixed inset-0 transition-opacity">
          <div class="absolute inset-0 bg-gray-900 opacity-75" />
        </div>
        <span class="hidden sm:inline-block sm:align-middle sm:h-screen">&#8203;</span>
        <div class="inline-block align-center bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full" role="dialog" aria-modal="true" aria-labelledby="modal-headline">
            <div class="divide-y-4">
              <div class="md:p-[40px] hidden md:block">
                <button type="button" class="py-2 px-2" @click="toggleModal()"><span><img src="@/assets/images/svg/cross.svg" alt=""></span></button>
                <p class="leading-[32px] text-[24px] font-[400] mt-[20px] text-[#151414]">Cancel trip request</p>
                <p class="leading-[20px] text-[14px] font-[400] mt-[4px] text-[#151414]">Please share your reasons for cancelling to help us serve you better.</p>
              </div>
              <div class="block md:hidden py-2 px-[18px]">
                <button type="button" class="py-2 px-2 leading-[24px] text-[16px] font-[500] flex justify-between items-center w-full" @click="toggleModal()">Cancel trip request<span><img src="@/assets/images/svg/down-arrow.svg" alt=""></span></button>
              </div>


              <div class="px-[20px] md:p-[40px] w-full md:w-[520px] leading-[24px] text-[16px] font-[400] text-[#151414]">
                <p class="leading-[20px] text-[14px] font-[400] mt-[4px] text-[#151414] md:hidden mt-[16px]">Please share your reasons for cancelling to help us serve you better.</p>
                <div class="form-check flex justify-between w-full mt-[16px] md:mt-0">
                  <label class="inline-block text-gray-800"> Bid price is high </label>
                  <input value="Bid price is high" v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>

<!--                2nd-->

                <div class="form-check flex justify-between w-full mt-[20px]">
                  <label class="inline-block text-gray-800">Date change </label>
                  <input value="Date change" v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>
                <!--                3rd-->

                <div class="form-check flex justify-between w-full mt-[20px]">
                  <label class="inline-block text-gray-800">Test purpose </label>
                  <input value="Test purpose" v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>

                <!--                4th-->

                <div class="form-check flex justify-between w-full mt-[20px]">
                  <label class="inline-block text-gray-800"> No bid showing </label>
                  <input value="No bid showing " v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>

                <!--                5th-->

                <div class="form-check flex justify-between w-full mt-[20px]">
                  <label class="inline-block text-gray-800">Location change </label>
                  <input value="Location change" v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>

                <!--                6th-->

                <div class="form-check flex justify-between w-full mt-[20px]">
                  <label class="inline-block text-gray-800">Other </label>
                  <input value="Other" v-model="cancelCauseType" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
                </div>
                <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
                </div>

                <div>
               <textarea v-if="cancelCauseTypeOther" class="border border-[#DBDBDB] placeholder-black px-4 py-2 w-full bg-[#F7F7F7] outline-none" placeholder="Enter cancellation reason">

               </textarea>
                  <div class="flex justify-evenly p-4 leading-[20px] text-[14px] font-[500]">
                      <button class="text-[#f04935] border border-[#808083] rounded-full text-center px-4 md:px-8 py-2">No, Thanks</button>
                      <button class="text-white border border-[#f04935] bg-[#f04935] rounded-full text-center px-4 md:px-8 py-2">Cancel request</button>
                  </div>
                </div>
              </div>
            </div>


        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  setup(){
    const cancelCauseType = ref('')
    const cancelCauseTypeOther = ref(false)
    const toggleModal = () => {
      document.getElementById('modal').classList.toggle('hidden')
    };

    watch(() => cancelCauseType.value, (currentValue) => {
      cancelCauseTypeOther.value = currentValue === "Other";
    });
    return{
      toggleModal, cancelCauseType, cancelCauseTypeOther
    }
  }
}
</script>