<template>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="">
        <label for="title" class="font-bold block mb-2">Title</label>
        <input  id="title" name="title" type="text" class="block w-full p-4 border border-[#ccc]" ref="titleInput" />
      </div>

        <div class="">
        <label for="description" class="font-bold block mb-2">Description</label>
        <textarea  id="description" name="description" rows="3" class="block w-full p-4 border border-[#ccc]" ref="descInput"></textarea>
      </div>
        <div class="">
        <label for="link" class="font-bold block mb-2">Title</label>
        <input id="link" name="link" type="url" class="block w-full p-4 border border-[#ccc]" ref="linkInput"/>
      </div>
      <div>
          <base-button type="submit"> Add Resource</base-button>
      </div>
    </form>
  </base-card>

</template>

<script>
import { inject } from 'vue';


export default{
    inject:['addResource'],
    methods:{
        submitData(){
            console.log("aaaaaaaaaa");
            const enteredTitle =this.$refs.titleInput.value;
            const enteredDescription =this.$refs.descInput.value;
            const entererLink =this.$refs.linkInput.value;
            this.addResource(enteredTitle,enteredDescription,entererLink);

            console.log("test======>",enteredTitle,enteredDescription,entererLink)
        }
    }
}
</script>
