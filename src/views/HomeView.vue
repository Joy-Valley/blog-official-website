<script setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { TextPlugin } from 'gsap/TextPlugin'
import { onMounted } from 'vue'

gsap.registerPlugin(ScrollTrigger)
gsap.registerPlugin(TextPlugin)

onMounted(() => {

})
</script>

<template>
  <div class="max-w-full overflow-hidden">
    <div class="min-h-[698px] pt-24">
      <div class="flex flex-col items-center gap-3">
        <h1 class="text-slate-700 text-5xl font-semibold">现代化响应式 <span
          class="font-semibold text-indigo-600">博客界面</span></h1>
        <p class="text-lg text-slate-500 font-semibold">使用 Vue3 + Nuxt.js + Tailwind CSS + ShadcnUI 开发</p>
        <a href="#">
          <div class="text-white bg-slate-800 rounded-full py-2.5 px-5 text-lg font-semibold">查看DEMO主页</div>
        </a>
      </div>
      <div class="mx-auto w-[80vw] h-[45vw] rounded-2xl border-slate-700 border-[24px] border-solid mt-[60px]"></div>
    </div>

    <div class="bg-white min-h-[698px] py-8">
      <div class="flex flex-col items-center gap-3 py-8">
        <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">响应式设计</div>
        <div class="text-2xl font-semibold">一站适配，无缝体验</div>
      </div>
      <div class="flex items-end">
        <div class="w-[64vw] h-[36vw] rounded-2xl border-slate-700 border-[24px] border-solid"></div>
        <div class="w-[28vw] h-[34vw] rounded-2xl border-slate-700 border-[20px] border-solid"></div>
        <div class="w-[18vw] h-[32vw] rounded-2xl border-slate-700 border-[20px] border-solid"></div>
      </div>
    </div>

    <div class="w-full h-[1080px] relative">
      <div class="w-[1920px] h-[1080px] bg-[#242424] min-h-[698px] py-8 absolute top-0 left-1/2 -translate-x-1/2">
        <div class="flex flex-col items-center gap-3 py-8">
          <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">瀑布流布局</div>
          <div class="text-2xl font-semibold text-gray-100">创意无限，内容流动</div>
        </div>
      </div>
    </div>


  </div>
</template>

<style lang="postcss">

</style>
