<script lang="ts" setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { TextPlugin } from 'gsap/TextPlugin'
import { onMounted, ref } from 'vue'
import ArticleCard from '@/components/ArticleCard.vue'
import type { Article } from '@/types'

const articleList = ref<Article[]>([
  {
    title: '皇甫松，字子奇，自号檀栾子',
    description: '多少恨，昨夜梦魂中。还似旧时游上苑，车如流。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: 'https://source.unsplash.com/random/700x600'
  },
  {
    title: '汤之问棘也是已：穷发之北，有冥海者，天池也。有鱼焉，...',
    description: '多少恨，昨夜梦魂中。还似旧时游上苑，车如流。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: 'https://source.unsplash.com/random/800x600'
  },
  {
    title: '山木，自寇也；膏火，自煎也。桂可食，故伐之；漆可用，...',
    description: '观夫明堂之宏壮也，则突兀瞳曨，乍明乍蒙，若大古元气之结空。巃嵸颓沓，若嵬若嶪，似天阃地门之开阖。尔乃划岝峉以岳立，郁穹崇而鸿纷。冠百王而垂勋，烛万象而腾文。窙惚恍以洞启，呼嵌岩而傍分。又比乎昆山之天柱，矗九霄而垂云。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: 'https://source.unsplash.com/random/802x600'
  },
  {
    title: '汤之问棘也是已：穷发之北，有冥海者，天池也。有鱼焉，其...',
    description: '学而时习之,不亦说乎?有朋自远方来,不亦乐乎?人不知而不愠,不亦君子乎?',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: 'https://source.unsplash.com/random/802x600'
  },
  {
    title: '大弦嘈嘈如急雨，小弦切切如私语。嘈嘈切切错杂弹，大珠...',
    description: '昔人已乘黄鹤去，此地空余黄鹤楼。黄鹤一去不复',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: 'https://source.unsplash.com/random/801x600'
  },
  {
    title: 'Title',
    description: 'The second item.',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: 'Title',
    description: 'The second item.',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: 'Title',
    description: 'The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: 'Title',
    description: 'The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.The second item.',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: 'Title',
    description: 'The second item.',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  }
])

gsap.registerPlugin(ScrollTrigger)
gsap.registerPlugin(TextPlugin)

onMounted(() => {
  ScrollTrigger.defaults({
    toggleActions: 'restart pause resume none'
    //markers:true
  })

  gsap.timeline()
    //标题1
    .fromTo('#title1', {
      duration: '',
      text: '现',
      ease: 'none'
    }, {
      duration: 1,
      text: '现代化响应式',
      ease: 'none'
    })
    //标题2
    .fromTo('#title2', {
      duration: '',
      text: '',
      ease: 'none'
    }, {
      duration: 1,
      text: '博客界面',
      newClass: 'font-semibold text-indigo-600',
      ease: 'none'
    })
    //查看Demo按钮
    .fromTo('#btn-lookDemo', {
      y: 50,
      scale: 0.5,
      opacity: 0
    }, {
      duration: 0.8,
      y: 0,
      scale: 1,
      opacity: 1
    })

  gsap.fromTo('#title3', {
    duration: '',
    text: '使用',
    ease: 'none'
  }, {
    duration: 2,
    text: '使用 Vue3 + Nuxt.js + Tailwind CSS + ShadcnUI 开发',
    ease: 'none'
  })

  gsap.from('#img1', { opacity: 0, scale: 1.5, y: -50, ease: 'power2.out', duration: 1.4 })

  //开头动画
  ScrollTrigger.create({
    trigger: '#screen1',
    start: 'top top',
    end: 'bottom',
    //markers: true,
    pin: true,
    scrub: 2
    //animation:
    //gsap.fromTo('#img1', { x: 0 }, { x: -200, scale: 0.7, ease: 'expoScale(0.5,7,none)' })
  })

  //响应式动画
  ScrollTrigger.create({
    trigger: '#sc2',
    start: 'top top',
    end: '+=1000',
    pin: true,
    //markers: true,
    id: 'sc2',
    scrub: 1,
    animation:
      gsap.timeline()
        .fromTo('#pc', { x: 300 }, { x: 40, direction: 1 })
        .fromTo('#ip', { x: 900 }, { x: -80, direction: 1 }, '<')
        .fromTo('#pe', { x: 900 }, { x: -120 }, '0.1').to('#pe', { x: -120, direction: 5 }, '1')
  })
  //瀑布流动画
  ScrollTrigger.create({
    trigger: '#sc3',
    start: 'top',
    end: 'bottom',
    pin: true,
    markers: true,
    id: 'sc3',
    scrub: 2,
    animation:
      gsap.timeline()
        /*.from('#title-pb',{
          y: -100,
          scale: 0.8,
          opacity: 0,
          stagger: 0.3,
          ease: 'power1.inOut',
          duration:1},'-2')*/
        /*.from('#sc3',{background:'#fff',duration:1,ease: "power1.out"})*/
        .from('#card', {
          y: -100,
          scale: 0.8,
          opacity: 0,
          stagger: 0.1,
          ease: 'power1.inOut',
          duration: 2
        }, '<')

  })

  //SSR动画
  ScrollTrigger.create({
    trigger: '#sc4',
    start: 'top top',
    end: 'bottom',
    pin: true,
    id: 'sc4',
    //scrub: true,
    animation:
      gsap.from('#img-ssr', {
        y: -50,
        scale: 0.5,
        opacity: 0,
        stagger: 0.2,
        ease: 'back.in'
      })
  })

  //个性化配色动画
  ScrollTrigger.create({
    trigger: '#sc6',
    start: 'top',
    end: '+=3000',
    pin: true,
    scrub: 2,
    animation:
      gsap.to("#sc6-dark", {
        clipPath: "ellipse(100% 120% at 50% 0%)",
        duration: 1, // 你可以根据需要调整动画的持续时间
        ease: "power1.inOut"
      })
  })

  //所用技术动画
  ScrollTrigger.create({
    trigger: '#sc9',
    start: 'top +500',
    end: '+=2000',
    //pin: true,
    scrub: 1,
    animation:
      gsap.fromTo('#img-logo', { scale: 0.8 }, { scale: 1.2 })
  })

})

</script>

<template>
  <div class="max-w-full overflow-hidden">
    <!--顶部主页-->
    <div id="screen1" class="min-h-[900px] pt-24">
      <div class="flex flex-col items-center gap-3">
        <h1 class="text-slate-700 text-5xl font-semibold"><span id="title1">现代化响应式</span> <span
          id="title2" class="font-semibold text-indigo-600">博客界面</span></h1>
        <p id="title3" class="text-lg text-slate-500 font-semibold">使用 Vue3 + Nuxt.js + Tailwind CSS + ShadcnUI
          开发</p>
        <a href="#">
          <div id="btn-lookDemo" class="text-white bg-slate-800 rounded-full py-2.5 px-5 text-lg font-semibold">
            查看DEMO主页
          </div>
        </a>
      </div>
      <div id="img1"
           class="bg-pc bg-cover bg-no-repeat mx-auto w-[80vw] h-[45vw] rounded-2xl border-slate-700 border-[24px] border-solid mt-[60px]"></div>
    </div>
    <!--响应式-->
    <div id="sc2" class="bg-white min-h-[900px] py-8">
      <div class="flex flex-col items-center gap-3 py-8">
        <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          响应式设计
        </div>
        <div class="text-2xl font-semibold">一站适配，无缝体验</div>
      </div>
      <div class="flex items-end justify-center">
        <div id="pc"
             class="bg-pc bg-cover bg-no-repeat w-[64vw] h-[36vw] rounded-2xl border-slate-700 border-[24px] border-solid"></div>
        <div id="ip"
             class="bg-tablet bg-cover bg-no-repeat w-[28vw] h-[34vw] rounded-2xl border-slate-700 border-[20px] border-solid"></div>
        <div id="pe"
             class="bg-mobile bg-cover bg-no-repeat w-[18vw] h-[32vw] rounded-2xl border-slate-700 border-[20px] border-solid"></div>
      </div>
    </div>
    <!--瀑布流-->
    <div id="sc3" class="bg-[#242424] w-full h-[950px] relative overflow-hidden">
      <div class="w-[1920px] h-[950px] min-h-[698px] py-8 absolute top-0 left-1/2 -translate-x-1/2">
        <div class="flex flex-col items-center gap-3 py-8">
          <div id="title-pb"
               class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            瀑布流布局
          </div>
          <div id="title-pb" class="text-2xl font-semibold text-gray-100">创意无限，内容流动</div>
        </div>
        <div class="absolute left-1/2 -translate-x-1/2 flex w-fit gap-4">
          <div v-for="index in 7" :key="index" class="flex flex-col gap-4 w-[300px] odd:mt-6">
            <ArticleCard v-for="j in 4" :key="j" :article="articleList[Math.floor(Math.random() * 10)]" />
          </div>
        </div>
        <div
          class="absolute top-0 left-0 bottom-0 right-0 w-full bg-gradient-to-t from-[#242424] via-transparent to-transparent pointer-events-none">
        </div>
        <div class="absolute bottom-0 w-full bg-[#242424] py-8">
          <p class="text-center text-xl font-semibold text-white">
            动态的视觉效果、高度的灵活性和优化的用户体验，为内容展示提供了一种既美观又实用的解决方案</p>
        </div>
      </div>
    </div>
    <!--SSR-->
    <div id="sc4" class="bg-[#242424] min-h-[900px] py-8 flex flex-col gap-40">
      <div class="flex flex-col items-center gap-3 py-8">
        <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          SSR服务器渲染
        </div>
        <div class="text-white text-2xl font-semibold">即时渲染，SEO先行</div>
        <div class="text-white text-lg font-medium">
          对于搜索引擎优化而言，服务器端渲染是一大利器。它允许搜索引擎爬虫更有效地索引您的网页内容，提高网站在搜索结果中的排名，从而吸引更多用户。
        </div>
      </div>
      <div class="flex items-end justify-center">
        <div class="flex items-start gap-2">
          <div id="img-ssr" class="w-[100px] flex flex-col items-center justify-center gap-2">
            <img alt="" src="@/assets/image/internet.svg">
            <p class="text-white text-center text-lg font-semibold">用户请求</p>
          </div>
          <div id="img-ssr" class="w-[50px]">
            <img alt="" src="@/assets/image/arrow.svg">
          </div>
          <div id="img-ssr" class="w-[100px] flex flex-col items-center justify-center gap-2">
            <img alt="" src="@/assets/image/server.svg">
            <p class="text-white text-center text-lg font-semibold">服务器渲染HTML</p>
          </div>
          <div id="img-ssr" class="w-[50px]">
            <img alt="" src="@/assets/image/arrow.svg">
          </div>
          <div id="img-ssr" class="w-[100px] flex flex-col items-center justify-center gap-2">
            <img alt="" src="@/assets/image/device.svg">
            <p class="text-white text-center text-lg font-semibold">接收HTML/CSS
              JavaScript</p>
          </div>
          <div id="img-ssr" class="w-[50px]">
            <img alt="" src="@/assets/image/arrow.svg">
          </div>
          <div id="img-ssr" class="w-[120px] flex flex-col items-center justify-center gap-2">
            <img alt="" src="@/assets/image/internet.svg">
            <p class="text-white text-center text-lg font-semibold">客户端加载</p>
          </div>
          <div id="img-ssr" class="w-[50px]">
            <img alt="" src="@/assets/image/arrow.svg">
          </div>
          <div id="img-ssr" class="w-[120px] flex flex-col items-center justify-center gap-2">
            <img alt="" src="@/assets/image/window.svg">
            <p class="text-white text-center text-lg font-semibold">全部加载完成</p>
          </div>
        </div>
      </div>
    </div>
    <!--MarkDown-->
    <div id="sc5" class="bg-[#242424] min-h-[900px] py-8 flex justify-center gap-14">
      <div class="flex flex-col justify-center gap-3 py-8 w-[365px]">
        <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          MarkDown文章
        </div>
        <div class="text-white text-2xl font-semibold">简洁之美，效率之选</div>
        <div class="text-white text-lg font-medium">
          Markdown文章以其简洁易读的语法、跨平台兼容性和高效的内容管理，成为提升写作效率、确保文档可读性、并便于版本控制和多格式转换的理想选择。
        </div>
      </div>
      <div class="flex items-center justify-center">
        <div
          class="bg-markdown bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[24px] border-solid"></div>
      </div>
    </div>
    <!--个性化配色-->
    <div id="sc6" class="relative min-h-[900px]">
      <!--白-->
      <div id="sc6-white" class="absolute w-full bg-gradient-to-b from-[#FFFFFF] to-[#EBEBEB] py-8">
        <div class="flex flex-col items-center gap-3 py-8">
          <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            个性化配色
          </div>
        </div>
        <div class="flex items-center justify-center">
          <div
            class="bg-pc bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[24px] border-solid"></div>
        </div>
      </div>
      <!--黑-->
      <div id="sc6-dark" class="absolute w-full bg-[#242424] py-8">
        <div class="flex flex-col items-center gap-3 py-8">
          <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            个性化配色
          </div>
        </div>
        <div class="flex items-center justify-center">
          <div
            class="bg-pc-dark bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[24px] border-solid"></div>
        </div>
      </div>
    </div>
    <!--本项目所用技术-->
    <div id="sc9" class="technology min-h-[900px] py-8 overflow-hidden">
      <div class="top-1/2 left-1/2 -translate-x-1/2 h-[900px] w-[1366px] relative">
        <div class="absolute top-1/2 left-1/2 -translate-x-1/2 text-5xl font-bold">本项目所用技术</div>
        <div id="img-logo">
          <a class="absolute top-[250px] left-[113px]" href="https://developer.mozilla.org/zh-CN/docs/Web/CSS">
            <img alt="CSS Icon" src="@/assets/image/icon/CSS@1x.svg">
          </a>
          <a class="absolute top-[122px] left-[1103px]" href="https://eslint.org/">
            <img alt="EsLint Icon" src="@/assets/image/icon/EsLint@1x.svg">
          </a>
          <a class="absolute top-[543px] left-[1185px]" href="https://gsap.com/">
            <img alt="GSAP Icon" src="@/assets/image/icon/GSAP@1x.svg">
          </a>
          <a class="absolute top-[423px] left-[12px]" href="https://developer.mozilla.org/zh-CN/docs/Web/HTML">
            <img alt="HTML Icon" src="@/assets/image/icon/HTML@1x.svg">
          </a>
          <a class="absolute top-[100px] left-[34px]" href="https://developer.mozilla.org/zh-CN/docs/Web/JavaScript">
            <img alt="JavaScript Icon" src="@/assets/image/icon/JavaScript@1x.svg">
          </a>
          <a class="absolute top-[675px] left-[1234px]" href="https://mastergo.com/?">
            <img alt="MasterGO Icon" src="@/assets/image/icon/MasterGO@1x.svg">
          </a>
          <a class="absolute top-[134px] left-[342px]" href="https://nodejs.org/">
            <img alt="NodeJS Icon" src="@/assets/image/icon/NodeJS@1x.svg">
          </a>
          <a class="absolute top-[394px] left-[186px]" href="https://nuxt.com/">
            <img alt="Nuxt Icon" src="@/assets/image/icon/Nuxt@1x.svg">
          </a>
          <a class="absolute top-[426px] left-[423px]" href="https://pinia.vuejs.org/zh/">
            <img alt="Pinia Icon" src="@/assets/image/icon/Pinia@1x.svg">
          </a>
          <a class="absolute top-[324px] left-[1224px]" href="https://pnpm.io/">
            <img alt="PNPM Icon" src="@/assets/image/icon/PNPM@1x.svg">
          </a>
          <a class="absolute top-[712px] left-[115px]" href="https://postcss.org/">
            <img alt="Postcss Icon" src="@/assets/image/icon/Postcss@1x.svg">
          </a>
          <a class="absolute top-[732px] left-[741px]" href="https://www.shadcn-vue.com/">
            <img alt="Shadcn Icon" src="@/assets/image/icon/Shadcn@1x.svg">
          </a>
          <a class="absolute top-[637px] left-[273px]" href="https://tailwindcss.com/">
            <img alt="Tailwind Icon" src="@/assets/image/icon/Tailwind@1x.svg">
          </a>
          <a class="absolute top-[100px] left-[1280px]" href="https://www.typescriptlang.org/">
            <img alt="TypeScript Icon" src="@/assets/image/icon/TypeScript@1x.svg">
          </a>
          <a class="absolute top-[136px] left-[680px]" href="https://cn.vitejs.dev/">
            <img alt="Vite Icon" src="@/assets/image/icon/Vite@1x.svg">
          </a>
          <a class="absolute top-[466px] left-[900px]" href="https://cn.vuejs.org/">
            <img alt="Vue Icon" src="@/assets/image/icon/Vue@1x.svg">
          </a>
          <a class="absolute top-[216px] left-[931px]" href="https://vueuse.org/">
            <img alt="VueUse Icon" src="@/assets/image/icon/VueUse@1x.svg">
          </a>
        </div>

      </div>
    </div>
    <!--设计-->
    <div class="bg-white min-h-[900px] py-8">
      <div class="flex flex-col items-center gap-3 py-8">
        <div class="text-4xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          设计至代码，无缝对接
        </div>
        <div class="text-lg font-medium">让我们的设计不仅仅是纸上谈兵，而是真实地呈现在每一个用户的屏幕上。</div>
        <div class="text-lg font-medium">MasterGO自动布局 + Tailwind CSS设计系统，打造统一风格的前端页面。</div>
      </div>
      <div class="flex items-end justify-center">
        <iframe allowfullscreen height="750"
                src="https://mastergo.com/file/124228531584653?page_id=724:15510&source=iframe_share"
                style="border: 1px solid rgba(0, 0, 0, 0.1);"
                width="800"></iframe>
        <iframe allowfullscreen height="750"
                src="https://mastergo.com/file/124753209989828?page_id=:0579&source=iframe_share"
                style="border: 1px solid rgba(0, 0, 0, 0.1);"
                width="800"></iframe>
      </div>
    </div>
    <!--页脚-->
    <div class="flex items-center justify-center py-8 border-t-2">
      <a href="#">
        <div class="text-white bg-slate-800 rounded-full py-2.5 px-5 text-lg font-semibold">查看DEMO主页</div>
      </a>
    </div>
  </div>
</template>

<style lang="postcss">
.technology {
  background: linear-gradient(180deg, #FFFFFF 50%, #F3F3F3 100%);
}

.bg-pc {
  background-image: url('@/assets/image/pc.webp');
}

.bg-pc-dark {
  background-image: url('@/assets/image/pc_dark.webp');
}

.bg-tablet {
  background-image: url('@/assets/image/tablet.webp');
}

.bg-mobile {
  background-image: url('@/assets/image/mobile.webp');
}

.bg-markdown {
  background-image: url('@/assets/image/markdown.png');
}

#sc6-dark{
  clip-path: ellipse(60% 0% at 50% 0%);
}
</style>
