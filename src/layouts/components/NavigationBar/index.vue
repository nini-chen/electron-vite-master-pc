<script lang="ts" setup>
import { ref } from "vue"
import { useRouter } from "vue-router"
import { useUserStore } from "@/store/modules/user"
import { UserFilled, Search } from "@element-plus/icons-vue"
const router = useRouter()
const userStore = useUserStore()

const input1 = ref("")
/** 登出 */
const logout = () => {
  userStore.logout()
  router.push("/login")
}
</script>

<template>
  <div class="navigation-bar">
    <div class="my-20px mx-20px">
      <div class="icon-title"><img src="@/assets/images/login_ITC.png" /><span>营销乾坤袋</span></div>
    </div>
    <div class="w-60% mt-20px">
      <el-input
        v-model="input1"
        style="width: 100%"
        size="large"
        placeholder="输入文件标题/团队空间文件上传人"
        :prefix-icon="Search"
      />
    </div>
    <div class="right-menu">
      <el-dropdown class="right-menu-item">
        <div class="right-menu-avatar">
          <el-avatar :icon="UserFilled" :size="30" />
          <span>{{ userStore.username }}</span>
        </div>
        <template #dropdown>
          <el-dropdown-menu>
            <div class="right-menu-item-li">
              <el-dropdown-item
                ><el-icon><ChatLineSquare /></el-icon>消息通知</el-dropdown-item
              >
            </div>
            <div>
              <el-dropdown-item
                ><el-icon><View /></el-icon>意见反馈</el-dropdown-item
              >
            </div>
            <div>
              <el-dropdown-item
                ><el-icon><Download /></el-icon>下载内容</el-dropdown-item
              >
            </div>
            <div>
              <el-dropdown-item
                ><el-icon><User /></el-icon>个人中心</el-dropdown-item
              >
            </div>
            <div>
              <el-dropdown-item
                ><el-icon><Warning /></el-icon>关于平台</el-dropdown-item
              >
            </div>
            <!-- <el-dropdown-item divided @click="logout">
              <span style="display: block">退出登录</span>
            </el-dropdown-item> -->
          </el-dropdown-menu>
        </template>
      </el-dropdown>
      <Share class="right_icon" />
      <Refresh class="right_icon" />
      <SemiSelect class="right_icon" />
      <CloseBold class="right_icon" @click="logout" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.navigation-bar {
  height: 100px;
  overflow: hidden;
  display: flex;
  justify-content: space-between;
  background-image: url("@/assets/images/head.png");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  .hamburger {
    display: flex;
    align-items: center;
    height: 100%;
    padding: 0 15px;
    cursor: pointer;
  }
  .icon-title {
    display: flex;
    img {
      width: 62px;
      height: 40px;
    }
    span {
      font-weight: bold;
      font-size: 26px;
      color: #333333;
      line-height: 35px;
      margin-left: 10px;
    }
  }
  .breadcrumb {
    flex: 1;
    // // 参考 Bootstrap 的响应式设计将宽度设置为 576
    // @media screen and (max-width: 576px) {
    //   display: none;
    // }
  }
  .sidebar {
    flex: 1;
    // 设置 min-width 是为了让 Sidebar 里的 el-menu 宽度自适应
    min-width: 0px;
    :deep(.el-menu) {
      background-color: transparent;
    }
    :deep(.el-sub-menu) {
      &.is-active {
        .el-sub-menu__title {
          color: var(--el-color-primary) !important;
        }
      }
    }
  }
  .right-menu {
    margin-right: 10px;
    height: 100%;
    display: flex;
    align-items: center;
    .right-menu-item {
      padding: 0 10px;
      cursor: pointer;
      .right-menu-avatar {
        display: flex;
        align-items: center;
        .el-avatar {
          margin-right: 10px;
        }
        span {
          font-size: 16px;
        }
      }
      .right-menu-item-li {
        display: flex;
        align-items: center;
        .el-icon {
          margin-right: 10px;
          width: 1rem;
          height: 1rem;
        }
      }
    }
  }
  .right_icon {
    width: 1.5em;
    height: 1.5em;
    margin-right: 8px;
    color: #999999;
  }
}
</style>
