<template>
  <div w50rem h20rem p5 flex="~ col" justify-center items-center bg-dark>
    <div pt5>
      <dv-scroll-board ref="scrollBoard" :config="config" style="width:500px;height:220px" @mouseover="mouseoverHandler" @click="clickHandler" />
    </div>
    <div py5>
      <button btn @click="updateRows">
        UpdateRows
      </button>
    </div>
  </div>
</template>
<script lang="ts" setup>
import type { ScrollBoard } from '@luyinghao159/datav-vue3/index'
const config = reactive({
  header: ['列1', '列2', '列3'],
  data: [
    ['<span style="color:#37a2da;">行1列1</span>', '行1列2', '行1列3'],
    ['行2列1', '<span style="color:#32c5e9;">行2列2</span>', '行2列3'],
    ['行3列1', '行3列2', '<span style="color:#67e0e3;">行3列3</span>'],
    ['行4列1', '<span style="color:#9fe6b8;">行4列2</span>', '行4列3'],
    ['<span style="color:#ffdb5c;">行5列1</span>', '行5列2', '行5列3'],
    ['行6列1', '<span style="color:#ff9f7f;">行6列2</span>', '行6列3'],
    ['行7列1', '行7列2', '<span style="color:#fb7293;">行7列3</span>'],
    ['行8列1', '<span style="color:#e062ae;">行8列2</span>', '行8列3'],
    ['<span style="color:#e690d1;">行9列1</span>', '行9列2', '行9列3'],
    ['行10列1', '<span style="color:#e7bcf3;">行10列2</span>', '行10列3'],
  ],
  index: true,
  columnWidth: [50],
  align: ['center'],
})

const data2 = [
  ['<span style="color:#37a2da;">行1列1</span>', '行1列2', '行1列3'],
  ['行2列1', '<span style="color:#32c5e9;">行2列2</span>', '行2列3'],
  ['行3列1', '行3列2', '<span style="color:#67e0e3;">行3列3</span>'],
  ['行4列1', '<span style="color:#9fe6b8;">行4列2</span>', '行4列3'],
  ['<span style="color:#ffdb5c;">行5列1</span>', '行5列2', '行5列3'],
  ['行6列1', '<span style="color:#ff9f7f;">行6列2</span>', '行6列3'],
  ['行7列1', '行7列2', '<span style="color:#fb7293;">行7列3</span>'],
  ['行8列1', '<span style="color:#e062ae;">行8列2</span>', '行8列3'],
  ['<span style="color:#e690d1;">行9列1</span>', '行9列2', '行9列3'],
  ['行10列1', '<span style="color:#e7bcf3;">行10列2</span>', '行10列3'],
  ['行11列1', '<span style="color:#e7bcf3;">行11列2</span>', '行11列3'],
  ['行12列1', '<span style="color:#e7bcf3;">行12列2</span>', '行12列3'],
]

const mouseoverHandler = (e: any) => {
  console.log(e)
}

const clickHandler = (e: any) => {
  console.log(e)
}

const scrollBoard = ref<InstanceType<typeof ScrollBoard>>(null)

const updateRows = () => {
  if (scrollBoard.value)
    // 此处可以传第二个参数 index，指定下次滚动的起始行
    scrollBoard.value.updateRows(data2)
}
</script>
