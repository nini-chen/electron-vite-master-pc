<template>
  <div class="app-container home_admin">
    <div><img src="@/assets/images/company_profile_2.png" /> <span>公司介绍</span></div>
    <div><img src="@/assets/images/product_Introduction_2.png" /> <span>产品介绍</span></div>
    <div><img src="@/assets/images/case_study_2.png" /> <span>案例介绍</span></div>
    <div><img src="@/assets/images/solution_2.png" /> <span>解决方案</span></div>
    <div><img src="@/assets/images/value_2.png" /> <span>价值赋能</span></div>
    <div><img src="@/assets/images/team_2.png" @click="$router.push('/team')" /> <span>团队空间</span></div>
  </div>
</template>
<script setup>
// import { useRouter } from "vue-router"
// const router = useRouter()
// function goTeam() {
//   router.push({ path: "/table" })
// }
</script>

<style lang="scss" scoped>
.home_admin {
  display: flex;
  justify-content: space-between;
  margin-top: 50px;
  div {
    position: relative;
    span {
      min-width: 300px;
      position: absolute;
      left: 72%;
      top: 70%;
      transform: translate(-50%, -50%);
      font-weight: 600;
      font-size: 40px;
      color: #ffffff;
      line-height: 56px;
    }
  }
}
</style>
