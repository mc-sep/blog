<script setup lang="ts">
defineProps<{ links: Record<string, any[]> }>()

function slug(name: string) {
  return name.toLowerCase().replace(/[\s\\\/]+/g, '-')
}
</script>

<template>
  <div class="max-w-300 mx-auto">
    <div
      v-for="key, cidx in Object.keys(links)" :key="key" slide-enter
      :style="{ '--enter-stage': cidx + 1 }"
    >
      <h4 :id="slug(key)" class="mt-15 mb-2 font-bold text-center op75">
        {{ key }}
      </h4>
      <div
        class="links-grid py-2 max-w-500 w-max mx-auto"
        grid="~ cols-1 md:cols-2 gap-4"
        :class="links[key].length === 1 ? 'flex' : links[key].length > 2 ? 'lg:grid-cols-3' : ''"
      >
        <a
          v-for="item, idx in links[key]"
          :key="idx"
          class="item relative flex items-center"
          :href="item.link"
          target="_blank"
          :class="!item.link ? 'opacity-0 pointer-events-none h-0 -mt-8 -mb-4' : ''"
          :title="item.name"
        >
          <div v-if="item.logo" class="pt-2 pr-5">
            <div class="text-3xl">
              <img :src="item.logo" :alt="item.name" class="w-15 h-15">
            </div>
          </div>
          <div class="w-200px flex-auto text-truncate">
            <div class="text-normal text-truncate">{{ item.name }}</div>
            <div class="desc text-sm opacity-50 font-normal text-truncate" v-html="item.desc" />
          </div>
        </a>
      </div>
    </div>
    <div class="prose pb5 mx-auto mt20">
      <div op75>
        <blockquote>
          <p class="font-bold text-18px">
            欢迎各位提交友链，请按照以下格式提交 <i class="i-twemoji-winking-face-with-tongue" />
          </p>
          <p>name: 'isYangs Blog (站点名称)'</p>
          <p>link: 'https://isyangs.cn (站点链接)'</p>
          <p>desc: '一个前端Bug构造师的博客 (站点描述)'</p>
          <p>logo: 'https://7.isyangs.cn/8/655c9835780a0-8.jpg (站点图标)'</p>
        </blockquote>
      </div>
    </div>
  </div>
</template>

<style scoped>
.links-grid a.item {
  font-size: 1.1rem;
  width: 300px;
  padding: 0.5rem 0.875rem 0.875rem;
  border-radius: 6px;
  opacity: .8;
}

.links-grid a.item:hover {
  opacity: 1;
  background: #88888811;
}
</style>
