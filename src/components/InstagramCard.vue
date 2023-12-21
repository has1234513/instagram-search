<template>
  <div class="container max-w-md border border-grey-light m-4">
  <div class="flex items-center px-6 py-4">
    <img :src="data.user.profile_picture" alt="Tamizhographer" class="rounded-full w-12 h-12">
    <div class="font-bold ml-4 text-sm lowercase">
      <span class="block"> {{data.user.username}} </span>
    </div>
  </div>
  <img :src="data.images.standard_resolution.url" alt="" class="block w-full">
  <div class="flex px-6 py-4 justify-between">
    <div class="flex">

      <svg class="block mr-4 h-6 text-red" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path  d="M10 3.22l-.61-.6a5.5 5.5 0 0 0-7.78 7.77L10 18.78l8.39-8.4a5.5 5.5 0 0 0-7.78-7.77l-.61.61z"></path></svg>
        <div class="text-sm pr-6 font-bold">
            {{data.likes.count}}
        </div>
      <svg class="block mr-4 h-6" viewBox="0 0 20 20" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
          <g id="icon-shape">
            <path fill="#000" d="M10,15 L18.0092049,15 C19.1017876,15 20,14.1019465 20,12.9941413 L20,3.00585866 C20,1.89706013 19.1086907,1 18.0092049,1 L1.99079514,1 C0.898212381,1 0,1.89805351 0,3.00585866 L0,12.9941413 C0,14.1029399 0.891309342,15 1.99079514,15 L6,15 L6,19 L10,15 Z M5,7 L7,7 L7,9 L5,9 L5,7 Z M9,7 L11,7 L11,9 L9,9 L9,7 Z M13,7 L15,7 L15,9 L13,9 L13,7 Z" id="Combined-Shape"></path>							
          </g>
        </g>
      </svg>
      <div class="text-sm pr-6 font-bold">
    {{data.comments.count}} 
  </div>
    </div>
  </div>
  <!-- <div class="text-sm  pb-4 px-6 font-bold">
    {{data.likes.count}} likes
  </div>
  <div class="text-sm  pb-4 px-6 font-bold">
    {{data.comments.count}} comments
  </div> -->


  <div v-html="formattedText"  class="text-sm px-6 py-2 leading-normal"></div>

  <div class="text-xs px-6 py-4 text-grey"> Created {{ formattedDate}} </div>

</div>
</template>

<script>

export default {

    props: {
        data: {
            type: Object,
            default: null,
        }
    },

    data() {
        return {
     
        }
    },

    computed: {
        formattedDate() {
            const date = new Date(this.data.created_time * 1000);
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            return date.toLocaleDateString("en-US", options);
        },
        formattedText() {
            const regex = /(@|#)\w+/g;
            return this.data?.caption?.text?.replace(regex, match => {
                return `<span class="text-blue-400">${match}</span>`;
            });
        }
    }

}
</script>

<style>

</style>