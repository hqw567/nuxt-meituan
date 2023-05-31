<script setup lang="ts">
const panel = ref([{
  tit: '了解更多',
  isOpen: false,
  data: [
    {
      title: '新闻中心',
    }, {
      title: '媒体资源',
    }, {
      title: '供应商',
    },
  ],
}, {
  tit: '加入我们',
  isOpen: false,
  data: [
    {
      title: '服务热线',
    }, {
      title: '服务热线',
    }, {
      title: '服务热线',
    },
  ],
}, {
  tit: '联系我们',
  isOpen: false,
  data: [
    {
      title: '服务热线',
    }, {
      title: '服务热线',
    }, {
      title: '服务热线',
    },
  ],
}])
function openPanel(index: number) {
  panel.value.map((ele, i) => {
    if (i === index)
      ele.isOpen = !ele.isOpen

    else
      ele.isOpen = false

    return ele
  })
}
</script>

<template>
  <div class="bg-[#f3f3f4] py-8 ">
    <div class="lg:m-auto lg:max-w-screen-xl">
      <div class="px-10 md:flex md:justify-between">
        <div class="text-sm text-slate-700 md:flex md:space-x-32 md:py-10">
          <div
            class="border-b py-2 flex justify-between
           items-center
          md:order-1 md:ml-32 md:text-base md:items-start md:flex-col  md:border-0"
          >
            <div class="md:mb-4">
              关注我们
            </div>
            <div class="text-lg space-x-3  flex md:flex-col md:space-x-0 md:space-y-4">
              <div>
                <Icon name="ri:weibo-fill" class="text-[#d62b2a]" />
                <span class="hidden md:inline-block text-sm ml-1">美团微博</span>
              </div>
              <div>
                <Icon name="ic:baseline-wechat" class=" text-[#00a800]" />
                <span class="hidden md:inline-block text-sm ml-1">美团微信公众号</span>
              </div>
              <div>
                <Icon name="grommet-icons:apple" class=" text-[#231f20]" />
                <span class="hidden md:inline-block text-sm ml-1">美团微信视频号</span>
              </div>
            </div>
          </div>
          <div
            v-for="(item, i) in panel" :key="item.tit" class="border-b md:border-0 transition-all

        "
          >
            <div class=" py-2 flex justify-between md:mb-4 md:text-base items-center" @click="openPanel(i)">
              <div>{{ item.tit }}</div>
              <div class="text-lg md:hidden">
                <Icon :name="item.isOpen ? 'mingcute:up-fill' : 'mingcute:down-fill'" />
              </div>
            </div>
            <div class=" text-sm transition-all md:block md:space-y-4" :class="{ hidden: !item.isOpen }">
              <div v-for="sub in item.data" :key="sub.title" class="py-2 md:py-0 md:h-6">
                {{ sub.title }}
              </div>
            </div>
          </div>
        </div>
        <div
          class="my-10 grid
      md:-order-last
      place-content-center"
        >
          <NuxtLink>
            <IconMeituan width="85px" height="30px" class="md:w-[113px] md:h-[40px]" />
          </NuxtLink>
        </div>
      </div>
      <div class=" text-xs text-center md:border-t md:py-8 pb-5">
        <div
          class=" space-y-2 text-slate-600 md:flex md:items-center px-10

      md:space-y-0
      md:divide-x"
        >
          <p>
            <NuxtLink class="border-b ">
              美团
            </NuxtLink> <span>©2023 美团版权所有</span>
          </p>
          <p>
            <NuxtLink class="border-b ">
              京ICP备10211739号
            </NuxtLink>
            <NuxtLink class="border-b ml-2 ">
              京公网安备 11000002002052号
            </NuxtLink>
          </p>
          <p>
            <NuxtLink class="border-b ">
              隐私政策
            </NuxtLink>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
