<script setup lang="ts">
import type { Article } from '@/types';
import { Avatar, AvatarImage } from '@/components/ui/avatar'
import image from '@/assets/image/avatar.jpeg'

interface Props {
	article: Article;
}

const props = defineProps<Props>();
</script>

<template>
	<div class="flex gap-2 items-center">
		<Avatar size="xs">
			<AvatarImage
				alt=""
				:src="image"
			/>
		</Avatar>
		<span class="text-slate-800">{{ props.article.authorName }}</span>
	</div>
</template>

<style scoped>

</style>
