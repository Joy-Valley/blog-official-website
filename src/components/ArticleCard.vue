<script lang="ts" setup>
import type { Article } from '@/types'
import { Card } from '@/components/ui/card'
import ArticleAuthor from '@/components/ArticleAuthor.vue'

interface Props {
  article: Article;
}

const props = defineProps<Props>()
</script>

<template>
  <Card class="w-full rounded-2xl overflow-hidden shadow bg-white">
    <img
      v-if="props.article.coverImageSrc"
      :src="props.article.coverImageSrc"
      alt=""
      class="aspect-video object-cover"
    >
    <div class="flex flex-col gap-3 p-4">
      <div class="flex gap-3 text-sm font-normal text-slate-500">
        <span>{{ props.article.category }}</span>
        <span>·</span>
        <span>{{ props.article.datetime }}</span>
      </div>
      <div class="flex flex-col gap-1.5">
        <h1 class="text-[1.375rem] font-medium line-clamp-2 text-slate-900">
          {{ props.article.title }}
        </h1>
        <h2 class="text-sm font-medium text-slate-700">
          {{ props.article.description }}
        </h2>
      </div>
      <ArticleAuthor :article="article" />
    </div>
  </Card>
</template>

<style scoped>

</style>
