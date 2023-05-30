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
  <div class="bg-[#f3f3f4] px-5 py-8 ">
    <div class="text-base text-slate-700">
      <div class="border-b py-2 flex justify-between">
        <div>关注我们</div>
        <div class="text-lg space-x-3">
          <Icon name="ri:weibo-fill" class="text-[#d62b2a]" />
          <Icon name="ic:baseline-wechat" class=" text-[#00a800]" />
          <Icon name="grommet-icons:apple" class=" text-[#231f20]" />
        </div>
      </div>
      <div v-for="(item, i) in panel" :key="item.tit" class="border-b transition-all">
        <div class=" py-2 flex justify-between" @click="openPanel(i)">
          <div>{{ item.tit }}</div>
          <div class="text-lg">
            <Icon :name="item.isOpen ? 'mingcute:up-fill' : 'mingcute:down-fill'" />
          </div>
        </div>
        <div class=" text-sm transition-all" :class="{ hidden: !item.isOpen }">
          <div v-for="sub in item.data" :key="sub.title" class="py-2">
            {{ sub.title }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
