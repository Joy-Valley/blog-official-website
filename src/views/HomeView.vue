<script lang="ts" setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { TextPlugin } from 'gsap/TextPlugin'
import { onMounted, ref } from 'vue'
import ArticleCard from '@/components/ArticleCard.vue'
import type { Article } from '@/types'

import image0 from '@/assets/image/image0.jpg'
import image1 from '@/assets/image/image1.jpg'
import image2 from '@/assets/image/image2.jpg'
import image3 from '@/assets/image/image3.jpg'
import image4 from '@/assets/image/image4.jpg'

const articleList = ref<Article[]>([
  {
    title: '皇甫松，字子奇，自号檀栾子',
    description: '多少恨，昨夜梦魂中。还似旧时游上苑，车如流。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: '汤之问棘也是已：穷发之北，有冥海者，天池也。有鱼焉，...',
    description: '多少恨，昨夜梦魂中。还似旧时游上苑，车如流。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: '山木，自寇也；膏火，自煎也。桂可食，故伐之；漆可用，...',
    description: '观夫明堂之宏壮也，则突兀瞳曨，乍明乍蒙，若大古元气之结空。巃嵸颓沓，若嵬若嶪，似天阃地门之开阖。尔乃划岝峉以岳立，郁穹崇而鸿纷。冠百王而垂勋，烛万象而腾文。窙惚恍以洞启，呼嵌岩而傍分。又比乎昆山之天柱，矗九霄而垂云。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: image2
  },
  {
    title: '汤之问棘也是已：穷发之北，有冥海者，天池也。有鱼焉，其...',
    description: '学而时习之,不亦说乎?有朋自远方来,不亦乐乎?人不知而不愠,不亦君子乎?',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: image3
  },
  {
    title: '大弦嘈嘈如急雨，小弦切切如私语。嘈嘈切切错杂弹，大珠...',
    description: '昔人已乘黄鹤去，此地空余黄鹤楼。黄鹤一去不复',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: image4
  },
  {
    title: '元嘉草草，封狼居胥，赢得仓',
    description: '北冥有鱼，其名为鲲。鲲之大，不知其几千里也。化而为鸟，其名为鹏。鹏之背，不知其几千里也。怒而飞，其翼若垂天之云。是鸟也，海运则将徙于南冥。南冥者，天池也。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: '小知不及大知，小年不及大年。奚以知其然也？朝菌不知晦...',
    description: '遥想公瑾当年，小乔初嫁了，雄姿英发。羽扇纶巾，谈笑间，樯橹灰飞烟灭。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: image1
  },
  {
    title: '司马光，字君实，号迂叟，陕州夏县涑水乡人，《宋史》，...',
    description: '蹴罢秋千，起来慵整纤纤手。露浓花瘦，薄汗轻衣透。见客入来，袜刬金钗溜。和羞走，倚门回首，却把青梅嗅。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59',
    coverImageSrc: image0
  },
  {
    title: '司马光，字君实，号迂叟，陕州夏县涑水乡人，《宋史》，...',
    description: '王守仁，汉族，幼名云，字伯安，号阳明，封新建伯，谥文成，人称王阳明。明代最著名的思想家、文学家、哲学家和军事家。王阳明不仅是宋明心学的集大成者，一生事功也是赫赫有名，故称之为“真三不朽”其学术思想在中国、日本、朝鲜半岛以及东南亚国家乃至全球都有重要而深远的影响，因此，王守仁和孔子、孟子、朱熹并称为孔、孟、朱、王。',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  },
  {
    title: '大弦嘈嘈如急雨，小弦切切如私语。嘈嘈切切错杂弹，大珠...',
    description: '昔人已乘黄鹤去，此地空余黄鹤楼。黄鹤一去不复',
    authorName: 'authorName',
    category: '分类', datetime: '2075 / 12 / 22 23:59'
  }
])

gsap.registerPlugin(ScrollTrigger)
gsap.registerPlugin(TextPlugin)

onMounted(() => {
  /*ScrollTrigger.defaults({
    toggleActions: 'restart pause resume none',
    //markers: {startColor: "green", endColor: "red", fontSize: "16px", fontWeight: "bold", indent: 20}
  })*/


  gsap.registerEffect({
    name: 'fadeOut',
    effect: (targets: any) => {
      return gsap.from(targets, {
        y: -20,
        opacity: 0,
        stagger: 0.3,
        duration: 2
      })
    },
    //default:{stagger:0.3},
    extendTimeline: true
  })

  const tl1 = gsap.timeline()
  tl1
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
    //描述
    .fromTo('#title3', {
      duration: '',
      text: '使用',
      ease: 'none'
    }, {
      duration: 2,
      text: '使用 Vue3 + Nuxt.js + Tailwind CSS + ShadcnUI 开发',
      ease: 'none'
    }, '<')
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
    }, '-=1')
    //查看Demo按钮
    .from('#btn-lookDemo', {
      y: 50,
      opacity: 0
    })

  //gsap.from('#img1', { opacity: 0, scale: 1.5, y: -50, ease: 'power2.out', duration: 1.4 })
  //gsap.set('#pc',{y:-200})

  //开头动画
  /*ScrollTrigger.create({
    trigger: '#sc1',
    start: 'top top',
    end: 'bottom',
    markers: true,
    pin: true,
  })*/

  //响应式动画
  ScrollTrigger.create({
    trigger: '#sc2',
    start: 'top top',
    end: 'bottom -500',
    pin: true,
    //markers: true,
    id: 'sc2'
  })
  const tl2 = gsap.timeline({
    scrollTrigger: {
      trigger: '#sc2',
      start: 'top 20%',
      end: 'bottom top',
      markers: true,
      scrub: 2
    }
  })
  tl2.fromTo('#pc', { y: -100, scale: 1.4 }, { y: 0, scale: 1, duration: 3 })
    .fromTo('#pc', { x: 300 }, { x: 40, delay: 0.3, duration: 2 })
    .fromTo('#ip', { x: 900 }, { x: -80, duration: 5, ease: 'power1.inOut' }, '<')
    .fromTo('#pe', { x: 900 }, { x: -120, duration: 5, ease: 'power1.inOut' }, '-=0.4')
    .from('#title-sc2', { y: 20, opacity: 0, stagger: 0.2, duration: 2 })

  // //瀑布流动画
  // ScrollTrigger.create({
  //   trigger: '#sc3',
  //   start: 'top',
  //   end: 'bottom',
  //   pin: true,
  //   //markers: true,
  //   id: 'sc3'
  // })
  // const tl3 = gsap.timeline({
  //   scrollTrigger: {
  //     trigger: '#sc3',
  //     start: 'top 80%',
  //     end: 'bottom 70%',
  //     scrub: 2
  //     //markers:true
  //   }
  // })
  // tl3
  //   .from('#card', {
  //     y: -100,
  //     scale: 0.8,
  //     opacity: 0,
  //     stagger: 0.1,
  //     ease: 'power1.inOut',
  //     duration: 2
  //   })
  //   .fadeOut('#title-pb', '-=2')


  //SSR动画
  ScrollTrigger.create({
    trigger: '#sc4',
    start: 'top top',
    end: 'bottom -200',
    pin: true,
    //markers:true,
    id: 'sc4'
  })
  const tl4 = gsap.timeline({
    scrollTrigger: {
      trigger: '#sc4',
      start: 'top 40%',
      end: 'bottom 60%',
      scrub: 2,
      id: 'ssr'
      //markers:true,
    }
  })
  tl4
    .fadeOut('#title-ssr')
    .from('#img-ssr', {
      x: -50,
      scale: 0.5,
      opacity: 0,
      stagger: 0.3,
      ease: 'power1.inOut',
      duration: 3
    })

  //markDown
  ScrollTrigger.create({
    trigger: '#sc5',
    start: 'top top',
    end: 'bottom -200',
    pin: true,
    id: 'sc5'
    //markers:true,
  })
  const tl5 = gsap.timeline({
    scrollTrigger: {
      trigger: '#sc5',
      start: 'top 60%',
      end: 'bottom 40%',
      scrub: 1
      //markers:true,
    }
  })
  tl5
    .from('#img-mkd', {
      x: 100,
      opacity: 0,
      scale: 1.2,
      ease: 'power2.out'
    })
    .from('#title-mkd', {
      x: 50,
      opacity: 0,
      stagger: 0.2
    })

  //个性化配色动画
  ScrollTrigger.create({
    id: 'sc6',
    trigger: '#sc6',
    start: 'top',
    end: 'bottom -200',
    pin: true
    //markers:true
  })
  gsap.to('#sc6-dark', {
    scrollTrigger: {
      trigger: '#sc6',
      start: 'top 40%',
      end: 'bottom 70%',
      scrub: 1
      //markers:true,
    },
    clipPath: 'ellipse(100% 120% at 50% 0%)',
    duration: 1, // 你可以根据需要调整动画的持续时间
    ease: 'power1.inOut'
  })

  //所用技术动画
  ScrollTrigger.create({
    trigger: '#sc9',
    start: 'top -50',
    end: 'bottom -200',
    //markers:true,
    pin: true
  })
  const tl9 = gsap.timeline({
    scrollTrigger: {
      trigger: '#sc9',
      start: 'top 70%',
      end: 'bottom 30%',
      scrub: 2
      //markers:true,
    }
  })
  tl9.fromTo('#img-logo', { scale: 0.7, y: 100 }, { scale: 1, y: 0, duration: 2, ease: 'power1.in' })
    .from('#title-js', { scale: 0.7, opacity: 0, duration: 1, ease: 'power3.Out' }, '-=1')

  //结尾
  ScrollTrigger.create({
    trigger: '#sc10',
    start: 'top top',
    end: 'bottom -100',
    //markers:true,
    pin: true
  })
  gsap.from('#title-sj', {
    scrollTrigger: {
      trigger: '#sc10',
      start: 'top 70%',
      end: 'bottom 50%',
      scrub: 2
    },
    y: -20,
    opacity: 0,
    stagger: 0.3
  })
})

</script>

<template>
  <div class="max-w-full overflow-hidden">
    <!--顶部主页-->
    <div id="sc1" class="min-h-[300px] pt-24">
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
      <!--      <div id="img1"
                 class="bg-pc bg-cover bg-no-repeat mx-auto w-[80vw] h-[45vw] rounded-2xl border-slate-700 border-[24px] border-solid mt-[60px] shadow-xl"></div>-->
    </div>
    <!--响应式-->
    <div id="sc2" class="min-h-[900px] py-8">
      <div class="flex flex-col items-center gap-3 py-8">
        <div id="title-sc2"
             class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-sky-500 to-indigo-500">
          响应式设计
        </div>
        <div id="title-sc2" class="text-2xl font-semibold">一站适配，无缝体验</div>
      </div>
      <div class="flex items-end justify-center">
        <div id="pc"
             class="bg-pc bg-cover bg-no-repeat w-[64vw] h-[36vw] rounded-2xl border-slate-700 border-[12px] border-solid"></div>
        <div id="ip"
             class="bg-tablet bg-cover bg-no-repeat w-[28vw] h-[34vw] rounded-2xl border-slate-700 border-[10px] border-solid"></div>
        <div id="pe"
             class="bg-mobile bg-cover bg-no-repeat w-[18vw] h-[32vw] rounded-2xl border-slate-700 border-[8px] border-solid"></div>
      </div>
    </div>
    <!--瀑布流-->
    <div id="sc3" class="bg-[#242424] w-full h-[1080px] relative overflow-hidden">
      <div class="w-[1920px] h-full min-h-[698px] py-8 absolute top-0 left-1/2 -translate-x-1/2">
        <div class="flex flex-col items-center gap-3 py-8">
          <div id="title-pb"
               class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            瀑布流布局
          </div>
          <div id="title-pb" class="text-2xl font-semibold text-gray-100">创意无限，内容流动</div>
        </div>
        <div class="absolute left-1/2 -translate-x-1/2 flex w-fit gap-4">
          <div v-for="index in 3" :key="index" class="flex flex-col gap-4 w-[300px] odd:mt-6">
            <ArticleCard v-for="j in 4" :key="j" class="article-card" :article="articleList[Math.floor(Math.random() * 10)]" />
          </div>
          <div class="flex flex-col gap-4 w-[300px] odd:mt-6">
            <ArticleCard class="article-card" id="main-card" :article="articleList[Math.floor(Math.random() * 10)]" />
            <ArticleCard class="article-card" :article="articleList[Math.floor(Math.random() * 10)]" />
            <ArticleCard class="article-card" :article="articleList[Math.floor(Math.random() * 10)]" />
            <ArticleCard class="article-card" :article="articleList[Math.floor(Math.random() * 10)]" />
          </div>
          <div v-for="index in 3" :key="index" class="flex flex-col gap-4 w-[300px] odd:mt-6">
            <ArticleCard v-for="j in 4" :key="j" class="article-card" :article="articleList[Math.floor(Math.random() * 10)]" />
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
        <div id="title-ssr"
             class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          SSR服务器渲染
        </div>
        <div id="title-ssr" class="text-white text-2xl font-semibold">即时渲染，SEO先行</div>
        <div id="title-ssr" class="text-white text-lg font-medium">
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
    <div id="sc5" class="bg-[#242424] h-[1000px] py-8 flex justify-center gap-14">
      <div class="flex flex-col justify-center gap-3 py-8 w-[365px] h-full">
        <div id="title-mkd"
             class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          MarkDown文章
        </div>
        <div id="title-mkd" class="text-white text-2xl font-semibold">简洁之美，效率之选</div>
        <div id="title-mkd" class="text-gray-100 text-lg font-light leading-relaxed">
          Markdown文章以其简洁易读的语法、跨平台兼容性和高效的内容管理，成为提升写作效率、确保文档可读性、并便于版本控制和多格式转换的理想选择。
        </div>
      </div>
      <div class="flex items-center justify-center">
        <div id="img-mkd"
             class="bg-markdown bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[16px] border-solid"></div>
      </div>
    </div>
    <!--个性化配色-->
    <div id="sc6" class="relative min-h-[1100px]">
      <!--白-->
      <div id="sc6-white" class="absolute h-full w-full bg-gradient-to-b from-[#FFFFFF] to-[#EBEBEB] py-8">
        <div class="flex flex-col items-center gap-3 py-8">
          <div
            class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            个性化配色
          </div>
        </div>
        <div class="flex items-center justify-center">
          <div
            class="bg-pc bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[16px] border-solid"></div>
        </div>
      </div>
      <!--黑-->
      <div id="sc6-dark" class="absolute h-full w-full bg-[#242424] py-8">
        <div class="flex flex-col items-center gap-3 py-8">
          <div
            class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
            个性化配色
          </div>
        </div>
        <div class="flex items-center justify-center">
          <div
            class="bg-pc-dark bg-cover bg-no-repeat w-[64vw] h-[40vw] rounded-2xl border-slate-700 border-[16px] border-solid"></div>
        </div>
      </div>
    </div>
    <!--本项目所用技术-->
    <div id="sc9" class="technology h-[1000px] py-8 overflow-hidden">
      <div class="left-1/2 -translate-x-1/2 w-[1366px] relative h-full">
        <div id="title-js" class="absolute top-1/2 left-1/2 -translate-x-1/2 text-5xl font-bold">本项目所用技术</div>
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
          <a class="absolute top-[700px] left-[741px]" href="https://www.shadcn-vue.com/">
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
    <div id="sc10" class="bg-white min-h-[1080px] py-8">
      <div class="flex flex-col items-center gap-3 py-8">
        <div id="title-sj"
             class="text-5xl leading-normal font-bold text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-blue-500">
          设计至代码，无缝对接
        </div>
        <div id="title-sj" class="text-lg font-medium">
          让我们的设计不仅仅是纸上谈兵，而是真实地呈现在每一个用户的屏幕上。
        </div>
        <div id="title-sj" class="text-lg font-medium">MasterGO自动布局 + Tailwind CSS设计系统，打造统一风格的前端页面。
        </div>
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

#sc6-dark {
  clip-path: ellipse(60% 0% at 50% 0%);
}

.pin-spacer-sc4 {
  background: #242424;
}

.pin-spacer-sc5 {
  background: #242424;
}
</style>
