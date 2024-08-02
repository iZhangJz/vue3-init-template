<template>
  <div class="home">
    <MdEditor :value="value" :handle-change="handleChange" />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import MdEditor from "@/components/MdEditor.vue"; // @ is an alias to /src

const value = ref("***欢迎使用 Vue3 前端万用模版***");

/**
 * 编辑器内容改变时触发
 * @param val
 */
const handleChange = (val: string) => {
  value.value = val;
};
</script>
