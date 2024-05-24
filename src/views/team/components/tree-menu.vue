<template>
  <div class="mytreestyle">
    <el-tree
      :indent="0"
      :data="data"
      :props="defaultProps"
      @node-click="handleNodeClick"
      node-key="id"
      :default-expanded-keys="[2, 3]"
    />
  </div>
</template>

<script lang="ts" setup>
interface Tree {
  id?: number
  label: string
  children?: Tree[]
}

const handleNodeClick = (data: Tree) => {
  console.log(data)
}

const data: Tree[] = [
  {
    label: "总裁精选"
  },
  {
    label: "维度总监精选"
  },
  {
    id: 2,
    label: "王者战队",
    children: [
      {
        label: "总经理精选"
      },
      {
        label: "重庆1部"
      },
      {
        label: "重庆2部"
      },
      {
        label: "贵州1部"
      },
      {
        label: "贵州2部"
      }
    ]
  },
  {
    id: 3,
    label: "亮剑队"
  },
  {
    id: 4,
    label: "西征战狼队"
  },
  {
    id: 5,
    label: "粤赣越勇队"
  },
  {
    id: 6,
    label: "王牌军团"
  }
]

const defaultProps = {
  children: "children",
  label: "label"
}
</script>

<style lang="scss" scoped>
.mytreestyle {
  width: 325px;
  height: 100vh;
  z-index: 99;
  padding: 10px 0;
  background: #fff;
  :deep(.el-tree-node) {
    position: relative;
    padding-left: 16px;
  }

  :deep(.el-tree-node__children) {
    padding-left: 16px;
  }

  :deep(.el-tree-node :last-child:before) {
    height: 38px;
  }

  :deep(.el-tree > .el-tree-node:before) {
    border-left: none;
  }

  :deep(.el-tree > .el-tree-node:after) {
    border-top: none;
  }

  :deep(.el-tree-node:before) {
    content: "";
    left: -4px;
    position: absolute;
    right: auto;
    border-width: 1px;
    border-left: 1px dashed #606266;
    bottom: 0px;
    height: 100%;
    top: -26px;
    width: 1px;
  }

  :deep(.el-tree-node:after) {
    content: "";
    left: -4px;
    position: absolute;
    right: auto;
    border-width: 1px;
    border-top: 1px dashed #606266;
    height: 20px;
    top: 12px;
    width: 18px;
  }

  :deep(.el-tree .el-tree-node__expand-icon.expanded) {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }

  :deep(.el-tree .el-icon-caret-right:before) {
    content: "";
    font-size: 16px;
    color: #606266;
    position: absolute;
    left: -20px;
    top: -8px;
  }

  :deep(.el-tree .el-tree-node__expand-icon.expanded.el-icon-caret-right:before) {
    content: "";
    font-size: 16px;
    color: #606266;
    position: absolute;
    left: -20px;
    top: -8px;
  }

  :deep(.el-tree-node__expand-icon.is-leaf:before) {
    content: "";
    font-size: 16px;
    color: #606266;
    position: absolute;
    left: -20px;
    top: -8px;
  }
  :deep(.el-tree-node__label) {
    min-width: 190px;
    background: #eeeeee;
    border-radius: 8px;
    height: 48px;
    font-size: 22px;
    align-items: center;
    display: flex;
    justify-content: start;
    padding-left: 10px;
  }
  :deep(.el-tree-node__content) {
    height: 50px;
    margin: 15px 0;
  }
  :deep(.el-tree-node__content:hover) {
    background-color: none;
  }
  :deep(.el-tree-node__content > .el-tree-node__expand-icon) {
    padding: 0;
    height: 50px;
  }
}
</style>
