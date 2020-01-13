<template>
  <a-tree
    :treeData="treeData"
    showIcon
    defaultExpandAll
    :defaultSelectedKeys="['0-0-0']"
  >
    <a-icon type="down" slot="switcherIcon" />
    <a-icon slot="smile" type="smile-o" />
    <a-icon slot="meh" type="smile-o" />
    <template slot="custom" slot-scope="{ icon }">
      <a-icon :type="icon" />-{{icon}}-
    </template>
  </a-tree>
</template>
<script>
const treeData = [
  {
    title: "parent 1",
    key: "0-0",
    slots: {
      icon: "smile"
    },
    children: [
      { title: "leaf", key: "0-0-0", icon: 'frown', slots: { icon: "meh" } },
      { title: "leaf", key: "0-0-1", icon: 'frown-o', scopedSlots: { icon: "custom" } }
    ]
  }
];

export default {
  data() {
    return {
      treeData
    };
  }
};
</script>
