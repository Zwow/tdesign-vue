<template>
  <div class="tdesign-demo-block-column-large">
    <div class="tdesign-demo-block-column">
      <!-- 方式一： t-tab-pannel 方式 -->
      <t-tabs v-model="value">
        <!-- 默认插槽 和 具名插槽（panel）都是用来渲染面板内容 -->
        <t-tab-panel value="first" label="选项卡1" :destroyOnHide="false">
          <p style="padding: 25px;">选项卡1的内容，使用 t-tab-pannel 渲染</p>
        </t-tab-panel>
        <t-tab-panel value="second" label="选项卡2" :destroyOnHide="false">
          <p slot="panel" style="padding: 25px;">选项卡2的内容，使用 t-tab-pannel 渲染</p>
        </t-tab-panel>
        <t-tab-panel value="third" label="选项卡3" :panel="panelRender" />
      </t-tabs>

      <!-- 方式二：使用 list 定义 Tab -->
      <t-tabs v-model="tab" :list="tabList" />
    </div>
  </div>
</template>

<script lang="jsx">
export default {
  data() {
    return {
      value: 'first',
      tab: 1,
      tabList: [
        // eslint-disable-next-line @typescript-eslint/no-unused-vars
        { label: '选项卡一', value: 1, panel: (h) => <p style="padding: 25px">这是选项卡一的内容，使用 t-tabs 渲染</p> },
        // eslint-disable-next-line @typescript-eslint/no-unused-vars
        { label: '选项卡二', value: 2, panel: (h) => <p style="padding: 25px">这是选项卡二的内容，使用 t-tabs 渲染</p> },
        // eslint-disable-next-line @typescript-eslint/no-unused-vars
        { label: '选项卡三', value: 3, panel: (h) => <p style="padding: 25px">这是选项卡三的内容，使用 t-tabs 渲染</p> },
      ],
    };
  },
  methods: {
    panelRender() {
      return <p style="padding: 25px;">选项卡3的内容，使用 t-tab-pannel 渲染</p>;
    },
  },
};
</script>
