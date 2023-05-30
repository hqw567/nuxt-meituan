<script setup lang="ts">
const isShowMenu = ref(false)
const menu = ref([{
  title: '首页',
  active: true,
}, {
  title: '和美团合作',
  active: false,
}, {
  title: '我们的科技',
  active: false,
}, {
  title: '企业社会责任',
  active: false,
  isChildden: true,
}, {
  title: '美团公益',
  active: false,
  isChildden: true,
}, {
  title: '投资者关系',
  active: false,
}, {
  title: '加入我们',
  active: false,
}])
</script>

<template>
  <div class="fixed top-0 left-0 w-[100%] ">
    <div class="xl:hidden">
      <div class="bg-white h-14 relative w-full flex justify-center items-center backdrop-blur">
        <div class=" absolute left-5 text-2xl">
          <Icon name="material-symbols:menu" color="black" @click="isShowMenu = !isShowMenu" />
        </div>
        <div class="">
          <IconMeituan />
        </div>
      </div>
      <div class=" fixed top-0 left-0 w-screen h-screen flex" :class="{ hidden: !isShowMenu }">
        <div class=" w-3/6 bg-white text-slate-700 h-screen px-5 py-8 pl-7 text-sm">
          <div>
            <IconMeituan />
          </div>
          <div class=" mt-7 mb-20 space-y-7">
            <div>首页</div>
            <div>和美团合作</div>
            <div>我们的科技</div>
            <div class="flex justify-between items-center">
              <span class="">企业社会责任</span>
              <Icon name="mingcute:right-fill" />
            </div>
            <div class="flex justify-between items-center">
              <span class="">美团公益</span>
              <Icon name="mingcute:right-fill" />
            </div>
            <div>投资者关系</div>
            <div>加入我们</div>
          </div>
          <div class="">
            <div class="mb-1">
              关注我们
            </div>
            <div class="text-2xl space-x-4">
              <Icon name="ri:weibo-fill" class="text-[#d62b2a]" />
              <Icon name="ic:baseline-wechat" class=" text-[#00a800]" />
              <Icon name="grommet-icons:apple" class=" text-[#231f20]" />
            </div>
            <div class="my-6 text-[16px] space-x-1">
              <span class=" text-slate-900">简体中文</span>
              <span>/</span>
              <span class=" text-slate-500">繁体中文</span>
            </div>
            <div>
              <button class="border shadow rounded px-2 py-1 hover:bg-slate-100">
                English Version
                <Icon name="iconoir:arrow-tr" class="black ml-2" />
              </button>
            </div>
          </div>
        </div>
        <div class=" w-3/6 h-screen bg-black/60" @click="isShowMenu = !isShowMenu" />
      </div>
    </div>
  </div>
  <div class="hidden xl:block fixed top-0 left-0 w-[100%]">
    <div class="flex justify-between items-center h-20 bg-white/70 shadow-md backdrop-blur-md backdrop-sepia px-10">
      <div class=" w-28 h-10">
        <IconMeituan class="w-[100%] h-[100%]" />
      </div>
      <div class="space-x-10 flex items-center h-[100%]">
        <div v-for="item in menu" :key="item.title" class="flex relative items-center space-x-1 cursor-pointer group h-[100%]">
          <div class="flex flex-col items-center">
            <span>{{ item.title }}</span>
            <span v-if="item.active" class=" w-6 rounded h-1 bg-[#ffd100]" />
            <span v-else class="w-0 group-hover:w-6 transition-[width] rounded h-1 bg-[#ffd100]" />
          </div>
          <Icon v-if="item.isChildden" name="icon-park-solid:down-one" />
          <div v-if="item.title === '美团公益'" class="invisible group-hover:visible   opacity-0 group-hover:opacity-100 transition-all absolute top-[84px] -left-7 bg-white shadow-2xl rounded-md p-1 space-y-3">
            <div class=" whitespace-nowrap cursor-pointer hover:bg-slate-100 rounded px-3 py-2">
              美团“乡村儿童操场”
            </div>
            <div class=" whitespace-nowrap cursor-pointer hover:bg-slate-100 rounded px-3 py-2">
              美团公益基金会
            </div>
          </div>
          <div
            v-if="item.title === '企业社会责任'"
            class="invisible group-hover:visible  opacity-0  group-hover:opacity-100 transition-all
            absolute top-[84px] -left-7 bg-white shadow-2xl rounded-md p-10 space-y-3"
          >
            <div class="flex border-b pb-5 space-x-24">
              <div>
                <div class=" text-lg font-bold pb-2 mb-5 border-b">
                  个体
                </div>
                <div class=" whitespace-nowrap space-y-5">
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div> <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                </div>
              </div>
              <div>
                <div class=" text-lg font-bold pb-2 mb-5 border-b">
                  个体
                </div>
                <div class=" whitespace-nowrap space-y-5">
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div> <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                </div>
              </div>
              <div>
                <div class=" text-lg font-bold pb-2 mb-5 border-b">
                  个体
                </div>
                <div class=" whitespace-nowrap space-y-5">
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                  <div class=" cursor-pointer">
                    便利用户生活
                  </div> <div class=" cursor-pointer">
                    便利用户生活
                  </div>
                </div>
              </div>
            </div>
            <div class=" text-center pt-4">
              报告中心
            </div>
          </div>
        </div>
      </div>
      <div class="flex space-x-10">
        <div class="flex items-center space-x-1">
          <span>关注我们</span>
          <Icon name="icon-park-solid:down-one" />
        </div>
        <div class="flex items-center space-x-1">
          <span>简体中文</span>
          <Icon name="icon-park-solid:down-one" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>

</style>
