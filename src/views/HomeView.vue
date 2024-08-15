<template>
  <div class="business">
    <t-table
      row-key="id"
      :data="data.list"
      :columns="columns"
      :loading="data.loading"
      :loadingProps="loadingProps"
      bordered
      size="medium"
      table-layout="auto"
      hover
    >
    </t-table>
  </div>
</template>

<script lang="tsx" setup>
import axios from 'axios';
import { ref, onMounted, reactive } from "vue";
import { type TableProps, MessagePlugin } from "tdesign-vue-next";
export interface data {
    loading: boolean;
    list: string;
}
const data: data = reactive({
  loading: true,
  list: [] as any
});
const loadingProps = {
  text: "加载中...",
}
const statusNameListMap: any = {
  0: {
    label: "维护中",
    icon: "paused-icon",
  },
  1: {
    label: "未知",
    icon: "unknow-icon",
  },
  2: {
    label: "可用",
    icon: "success-icon",
  },
  8: {
    label: "部分可用",
    icon: "paused-icon",
  },
  9: {
    label: "不可用",
    icon: "fail-icon",
  },
};
const columns = ref<TableProps["columns"]>([
  {
    colKey: "friendly_name",
    title: "服务名称",
    width: "70%",
  },
  {
    colKey: "status",
    title: "服务状态",
    cell: (h, { row }) => {
      return (
        <div
          class={`status-item status-icon ${statusNameListMap[row.status].icon}`}
        >
          {statusNameListMap[row.status].label}
        </div>
      );
    },
    width: "30%",
  },
]);
onMounted(() => {
  axios({
    method: "post",
    url: "https://api.uptimerobot.com/v2/getMonitors",
    data: {
      api_key: 'ur2396473-93c6e09626a1f6f335eace34',
      format: 'json',
      logs: 1,
    }
  }).then(res => {
    data.list = res.data.monitors ;
    data.loading = false;
    MessagePlugin.success('系统状态获取成功');
  }).catch(function (err) {
    if (err.response) {
      //console.log(err.response.data);
      //MessagePlugin.error(err.response.data);
      MessagePlugin.error(err.message);
      data.loading = false;
    } else if (err.request) {
      console.log(err.request);
      MessagePlugin.error(err.request);
      data.loading = false;
    } else {
      console.log('err', err.message);
      MessagePlugin.error(err.message);
      data.loading = false;
    }
  });
})
</script>
