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

//modal child
<template>
  <div class="font-inter">
<!--    <div class="flex items-center justify-center h-full">-->
<!--      <button class="border border-[#151414] w-[105px] rounded-full flex justify-center items-center leading-[16px] text-[12px] font-[500]" @click="toggleModal">Verify Trip</button>-->
<!--    </div>-->
    <div class="fixed z-10 overflow-y-auto top-0 w-full left-0" :class="props.show === true ? 'block' : 'hidden'" id="modal">
      <div class="flex items-center justify-center min-height-100vh pt-4 px-4 pb-20 text-center sm:block sm:p-0">
        <div class="fixed inset-0 transition-opacity">
          <div class="absolute inset-0 bg-gray-900 opacity-75" />
        </div>
        <span class="hidden sm:inline-block sm:align-middle sm:h-screen">&#8203;</span>
        <div class="inline-block align-center bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full" role="dialog" aria-modal="true" aria-labelledby="modal-headline">
          <div class="divide-y-4">
            <div class="md:p-[40px] hidden md:block">
              <button type="button" class="py-2 px-2" @click="$emit('closeModal')"><span><img src="@/assets/images/svg/cross.svg" alt=""></span></button>
              <p class="leading-[32px] text-[24px] font-[400] mt-[20px] text-[#151414]" @click="$emit('closeModal')">Cancel trip request</p>
              <p class="leading-[20px] text-[14px] font-[400] mt-[4px] text-[#151414]">Please share your reasons for cancelling to help us serve you better.</p>
            </div>
            <div class="block md:hidden py-2 px-[18px]">
              <button type="button" class="py-2 px-2 leading-[24px] text-[16px] font-[500] flex justify-between items-center w-full" @click="$emit('closeModal')">Cancel trip request<span><img src="@/assets/images/svg/down-arrow.svg" alt=""></span></button>
            </div>


            <div class="px-[20px] md:p-[40px] w-full md:w-[520px] leading-[24px] text-[16px] font-[400] text-[#151414]">
              <p class="leading-[20px] text-[14px] font-[400] mt-[4px] text-[#151414] md:hidden mt-[16px]">Please share your reasons for cancelling to help us serve you better.</p>
              <div class="form-check flex justify-between w-full mt-[16px] md:mt-0">
                <label class="inline-block text-gray-800"> Bid price is high </label>
                <input value="Bid price is high" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>

              <!--                2nd-->

              <div class="form-check flex justify-between w-full mt-[20px]">
                <label class="inline-block text-gray-800">Date change </label>
                <input value="Date change" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>
              <!--                3rd-->

              <div class="form-check flex justify-between w-full mt-[20px]">
                <label class="inline-block text-gray-800">Test purpose </label>
                <input value="Test purpose" name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>

              <!--                4th-->

              <div class="form-check flex justify-between w-full mt-[20px]">
                <label class="inline-block text-gray-800"> No bid showing </label>
                <input value="No bid showing "  name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>

              <!--                5th-->

              <div class="form-check flex justify-between w-full mt-[20px]">
                <label class="inline-block text-gray-800">Location change </label>
                <input value="Location change"  name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>

              <!--                6th-->

              <div class="form-check flex justify-between w-full mt-[20px]">
                <label class="inline-block text-gray-800">Other </label>
                <input value="Other"  name="cancellationCause" class="form-check-input float-left mt-1 mr-2 h-4 w-4 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white bg-contain bg-center bg-no-repeat align-top transition duration-200 checked:border-red-600 checked:bg-red-600 focus:outline-none" type="radio" />
              </div>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px]">
              </div>

              <div>

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
  props:['show'],
  emits: ['closeModal'],
  setup(props){
    return{
      props
    }
  }
}
</script>

// modal parent

<template>
  <div class="bg-[#F7F7F7] md:bg-[#FeF8F7] md:pt-[40px] font-inter">
    <div class="max-w-[600px] mx-auto bg-[#F7F7F7] md:bg-[#FFFFFF]">
      <div class="p-[16px] md:p-[44px] hidden md:block">
        <img src="@/assets/images/svg/left-arrow.svg" class="h-[16px] w-[16px]" alt="">
        <div class="flex justify-between mt-[20px]">
          <p class="leading-[32px] text-[24px] font-[400] text-[#151414]">Trip #450341</p>
            <a href="#" class="border border-[#151414] w-[105px] rounded-full flex justify-center items-center leading-[16px] text-[12px] font-[500]" @click="toggleModal()"> Verify trip</a>

        </div>
        <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
        </div>
<!--        desktop notifications -->
<RentalNotification :body="textBody" />
      </div>
      <!--      phone head-->
      <div class="px-[16px] pb-[16px] pt-[36px] md:pt-0s md:p-[44px] bg-[#f04935] block md:hidden">
        <img src="@/assets/images/svg/white-left-arrow.svg" class="h-[16px] w-[16px]" alt="">
        <div class="flex justify-between mt-[20px]">
          <p class="leading-[32px] text-[24px] font-[400] text-white">Car Details</p>
          <a href="#" class="border border-white text-white w-[105px] rounded-full flex justify-center items-center leading-[16px] text-[12px] font-[500]" @click="toggleModal()"> Verify trip</a>
        </div>
      </div>
      <!--        phone notifications -->
      <div class="block md:hidden">
        <RentalNotification :body="textBody" />
      </div>

     <div class="p-[16px] md:px-[40px] md:pt-[20px]">
        <div class="flex gap-x-[20px]">
          <img src="@/assets/images/svg/red-car.svg" alt="">
          <div>
            <p class="leading-[28px] text-[20px] font-[500]">Red Kia Sportage</p>
            <small class="text-[#8D8D8F] leading-[20px] text-[14px] block">DHA 40127211</small>
            <small class="text-[#8D8D8F] leading-[20px] text-[14px]">4 Seat capacity, AC</small>
          </div>
        </div>
     </div>



      <div class="bg-[#C9CDD1] h-[4px] w-full mt-[16px] bg-opacity-50">
      </div>
      <div class="p-[16px] md:px-[40px] md:pt-[20px]">
        <div class="flex justify-between">
          <p class="leading-[17px] text-[14px] font-[400]">Total fare</p>
          <p class="leading-[28px] text-[20px] font-[500] text-right">BDT 2450</p>
        </div>
      </div>

      <div class="bg-[#C9CDD1] h-[4px] w-full mt-[16px] bg-opacity-50">
      </div>

<!--      Step Progress-->
      <div class="p-[16px] md:px-[40px] md:pt-[20px]">
        <div class="wrapper">
          <ul class="StepProgress">
            <li class="StepProgress-item"><strong>Banani, Dhaka</strong>
              <p class="leading-[16px] text-[12px] font-[400] text-[#8D8D8F] mt-1">Road 57, Block B, Banani, Dhaka</p>
              <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
              </div>
            </li>
            <li class="StepProgress-item"><strong>WaterAid Bangladesh</strong>
              <p class="leading-[16px] text-[12px] font-[400] text-[#8D8D8F] mt-1">Bangladesh, Dhaka, Rd No #23</p>
            </li>
          </ul>
        </div>
      </div>

      <div class="bg-[#C9CDD1] h-[4px] w-full mt-[16px] bg-opacity-50">
      </div>

      <div class="p-[16px] md:px-[40px] md:pt-[20px]">
        <div class="flex justify-between ">
          <div>
            <p class="text-[#8D8D8F] leading-[14px] text-[12px] font-[500]">JOURNEY DATE & TIME</p>
            <p class="text-[#212529] leading-[20px] text-[16px] font-[500] mt-[6px]">08:00 PM, Thu, 20 Feb 2020</p>
          </div>
          <a href="#" class="border border-white bg-[#EDEDED] text-[#676769] w-[102px] rounded-full flex justify-center items-center leading-[18px] text-[12px] font-[500]">Set reminder</a>
        </div>
        <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
        </div>
        <div class="flex justify-between mt-[16px]">
          <p class="leading-[17px] text-[14px] font-[400]">Round Trip</p>
          <p class="leading-[28px] text-[20px] font-[500] text-right">Yes</p>
        </div>
        <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
        </div>

        <div class="flex justify-between mt-[16px]">
          <p class="leading-[17px] text-[14px] font-[400]">Return Date</p>
          <p class="leading-[19px] text-[16px] md:leading-[28px] md:text-[20px] font-[500] text-right">10:30 AM, 21 Feb, 2021</p>
        </div>
        <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
        </div>

        <div class="flex justify-between mt-[16px]">
          <p class="leading-[17px] text-[14px] font-[400]">Promo Selected</p>
          <p class="leading-[26px] text-[18px] md:leading-[28px] md:text-[20px] font-[500] text-right">CAR100</p>
        </div>
        <div class="bg-[#C9CDD1] h-[1px] w-full mt-[16px] bg-opacity-50">
        </div>

        <div class="mt-[16px]">
          <p class="leading-[17px] text-[14px] font-[500] text-[#151414]">Additional note</p>
          <p class="leading-[20px] text-[14px] font-[400] mt-[10px]">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cursus et, integer posuere nullam dignissim suspendisse nulla. Cum ornare fringilla eget sed risus, sed.</p>
        </div>
      </div>

      <div class="bg-[#C9CDD1] h-[4px] w-full mt-[16px] bg-opacity-50">
      </div>



      <div class="p-[16px] md:pt-[20px] md:px-[40px]">
          <p class="text-[#8D8D8F] leading-[15px] text-[12px] font-[500] uppercase">Partner info</p>
        <div class="flex gap-x-[20px] mt-[9px]">
          <img src="@/assets/images/svg/blue-car.svg" alt="">
          <div>
            <p class="leading-[24px] text-[16px] md:leading-[28px] md:text-[20px] font-[500]">Sohan Rent a Car</p>
            <small class="text-[#8D8D8F] leading-[20px] text-[14px] block">Kalabagan, Dhaka</small>
          </div>
          <a href="#" class="block md:hidden bg-[#48A43F] bg-opacity-40 text-[#48A43F] w-[30%] rounded-full flex justify-center items-center text-[10px] font-[500] ml-auto">
            <span class="block mr-2"><img src="@/assets/images/svg/green-phone.svg" alt=""></span>
            Call</a>
        </div>

    </div>

      <div class="bg-[#C9CDD1] h-[4px] w-full mt-[16px] bg-opacity-50">
      </div>

      <div class="p-[16px] md:pt-[20px] md:px-[40px]">
        <p class="text-[#8D8D8F] leading-[15px] text-[12px] font-[500] uppercase">Driver info</p>
        <div class="flex gap-x-[20px] mt-[9px] items-center">
          <img src="@/assets/images/svg/user.svg" alt="">
          <div>
            <p class="text-[#8D8D8F] leading-[24px] text-[16px] font-[400] block">A driver will be assigned to you soon</p>
          </div>
        </div>
        <div class="border border-[#DBDBDB] w-full rounded-lg mt-[30px] hidden md:block">
          <div class="divide-x py-[10px] flex justify-between">
            <div class="w-1/2 flex flex-col justify-center items-center">
              <p class="text-[#8D8D8F] leading-[12px] text-[10px]">Jatri Helpline</p>
              <p class="text-[#151414] leading-[24px] text-[14px] font-[500]">+38763487</p>
            </div>
            <div class="w-1/2 flex flex-col justify-center items-center">
              <p class="text-[#8D8D8F] leading-[12px] text-[10px]">National helplinee</p>
              <p class="text-[#151414] leading-[24px] text-[14px] font-[500]">999</p>
            </div>
          </div>
        </div>
        <a href="#" class="block md:hidden text-[#f04935] border border-[#808083] w-full rounded-full flex justify-center items-center text-[10px] font-[500] mt-[20px] py-3">
          <span class="block mr-2"><img src="@/assets/images/svg/jatri-logo.svg" alt=""></span>
          Call center</a>

      </div>


    </div>
    <RentalVerifyTrip
    :show="show"
    @closeModal="toggleModal"
    />
  </div>
</template>
<script>
import {ref} from 'vue';
export default {

  setup(){
    const textBody = ref('Your trip is confirmed. Partner will pick you up at the selected time. For additional instructions, please call partner. ');
    let show = ref(false);
    const toggleModal = () => {
      show.value = !show.value
    }
    return{
      textBody,
      show,
      toggleModal
    }
  }
}
</script>

<style>
.wrapper {
  width: 100%;
  font-family: 'inter';
  font-size: 14px;
}
.StepProgress {
  position: relative;
  padding-left: 45px;
  list-style: none;
}
.StepProgress-item:before {
  display: inline-block;
  content: '';
  position: absolute;
  top: 0;
  left: -30px;
  width: 10px;
  height: 100%;
  border-left: 2px solid #CCC;
}
.StepProgress-item:last-child::before {
  display: inline-block;
  content: '';
  position: absolute;
  top: 0;
  left: -30px;
  width: 10px;
  height: 100%;
  border-left: 0px;
}
.StepProgress-item {
  position: relative;
  counter-increment: list;
}

.StepProgress-item:not(:last-child) {
  padding-bottom: 20px;
}
.StepProgress-item::before {
  display: inline-block;
  content: '';
  position: absolute;
  left: -30px;
  height: 100%;
  width: 10px;
}
.StepProgress-item::after {
  content: '';
  display: inline-block;
  position: absolute;
  top: 0;
  left: -38px;
  width: 18px;
  height: 18px;
  border: 4px solid #fff;
  border-radius: 50%;
  background-color: #000;
}

.StepProgress-item:first-child::after {
  border-radius: 50%;
  background-color:#F04935
}

.StepProgress-item:last-child::after {
  border-radius: 0;
  background-color:#1E88E5
}
.StepProgress strong {
  display: block;
}
</style>