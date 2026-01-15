<script setup>
import { ref } from 'vue'

const file = ref(null)
const uploadedFile = ref(null)

const openInput = () => {
  file.value.click()

}
const uploadFile = () => {
    uploadedFile.value = file.value.files[0]
}

</script>
<template>
  <div class="bg-slate-400 min-h-screen flex justify-center items-center flex-col font-inter text-slate-80">
    <div class="text-5xl 0 font-bold">VauKonverter</div>
    <div class="bg-slate-400 flex flex-col gap-4 items-center border border-slate-600 rounded-xl border-dashed p-10 mt-5 w-[600px]">
      
      <img src="/public/upload.svg" class="w-40"/>
      <input class="hidden" type="file" ref="file" accept=".mp3" @change="uploadFile"/>
      <button class="py-2 px-4 rounded-lg border-slate-500 border-2 hover:bg-slate-500 transition duration-200 cursor-pointer" @click="openInput">Upload your .mp3 file</button>
      <div v-if="uploadedFile" class="flex flex-col">
       <p class="flex gap-2"><span class="font-bold">File chosen: </span> {{ uploadedFile.name }}</p>
       <button class="border-2 border-[#5985E1] rounded-lg py-1 px-2 mt-2 hover:bg-[#5985E1] hover:text-white transition duration-200 cursor-pointer">Convert to .wav</button>
      </div>  
    </div>
  </div>
</template>