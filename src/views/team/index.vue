<template>
  <div class="team_content" v-if="!fileType">
    <div class="top">
      <div>特战团队</div>
      <div>冠军团队</div>
      <div>南京分公司</div>
      <div>外贸部</div>
    </div>
    <div class="flex">
      <TreeMenu />
      <div class="content">
        <div class="card_box" @click="$router.push('/docxfile')">
          <div>
            <img src="@/assets/images/word_1.png" alt="" />
          </div>
          <div>
            <div class="file_name">远程视频会议文件</div>
            <div class="author">上传者：张某某</div>
          </div>
        </div>
        <div class="card_box" @click="$router.push('/excelfile')">
          <div>
            <img src="@/assets/images/Excel_1.png" alt="" />
          </div>
          <div>
            <div class="file_name">远程视频会议文件</div>
            <div class="author">上传者：张某某</div>
          </div>
        </div>
        <div class="card_box" @click="$router.push('/pdffile')">
          <div>
            <img src="@/assets/images/ppt_1.png" alt="" />
          </div>
          <div>
            <div class="file_name">远程视频会议文件</div>
            <div class="author">上传者：张某某</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import TreeMenu from "./components/tree-menu.vue"
</script>

<style scoped lang="scss">
.team_content {
  display: block;
  .content {
    margin-top: 80px;
    margin-left: 90px;
    display: grid;
    grid-gap: 20px;
    grid-template-columns: repeat(4, 1fr); /* 创建四个相等宽度的列 */
    grid-template-rows: repeat(2, 1fr); /* 创建两个相等高度的行 */
  }
  .card_box {
    background: #3d95e6;
    width: 346px;
    height: 400px;
    border-radius: 30px;
    overflow: hidden;
  }
  .file_name {
    font-weight: bold;
    font-size: 32px;
    color: #ffffff;
    line-height: 41px;
    text-align: center;
    padding-top: 20px;
  }
  .author {
    font-weight: bold;
    font-size: 24px;
    color: #ffffff;
    line-height: 31px;
    text-align: center;
    padding-top: 20px;
  }
}
.top {
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 65px;
  width: 100%;
  box-shadow: 0px 4px 10px 0px rgba(0, 0, 0, 0.1);
  z-index: 9990;
  div {
    padding: 0 30px;
    font-size: 20px;
    color: #333333;
    line-height: 28px;
  }
}
</style>
