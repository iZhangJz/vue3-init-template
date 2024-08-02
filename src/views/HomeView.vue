<template>
  <div class="home">
    <a-divider> Markdown 富文本编辑器 </a-divider>
    <MdEditor :value="mdValue" :handle-change="handleMdChange" />
    <a-divider> MonacoEditor 代码编辑器 </a-divider>
    <MonacoEditor :value="codeValue" :handle-change="handleCodeChange" />
    <a-divider> MonacoEditor Diff 代码编辑器 </a-divider>
    <DiffMonacoEditor
      :modified-model-value="modifiedValue"
      :original-model-value="originalValue"
      :handle-change="handleDiffCodeChange"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import MdEditor from "@/components/MdEditor.vue";
import MonacoEditor from "@/components/MonacoEditor.vue";
import DiffMonacoEditor from "@/components/MonacoDiffEditor.vue"; // @ is an alias to /src

const mdValue = ref("***欢迎使用 Vue3 前端万用模版***");
const codeValue = ref(
  "class Solution {\n" +
    "    public int[] twoSum(int[] nums, int target) {\n" +
    "        Map<Integer,Integer> hashtable = new HashMap<>();\n" +
    "        for(int i = 0;i < nums.length;i++){\n" +
    "            if(hashtable.containsKey(target-nums[i])){\n" +
    "                return new int[]{i,hashtable.get(target-nums[i])};\n" +
    "            }\n" +
    "            hashtable.put(nums[i],i);\n" +
    "        }\n" +
    "        return new int[0];\n" +
    "    }\n" +
    "}"
);
const modifiedValue = ref(
  "class Solution {\n" +
    "public:\n" +
    "    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {\n" +
    "        ListNode* dummy = new ListNode(-1, NULL);\n" +
    "        ListNode* cur = dummy;\n" +
    "        int carry = 0;\n" +
    "        int res = 0;\n" +
    "        while (l1 != NULL || l2 != NULL) {\n" +
    "            int x = l1 == NULL ? 0 : l1->val;\n" +
    "            int y = l2 == NULL ? 0 : l2->val;\n" +
    "            res = (x + y + carry) % 10;\n" +
    "            cur->next = new ListNode(res);\n" +
    "            cur = cur->next;\n" +
    "            carry = (x + y  + carry) / 10;\n" +
    "            l1 = l1 == NULL ? NULL : l1->next;\n" +
    "            l2 = l2 == NULL ? NULL : l2->next;\n" +
    "        }\n" +
    "        if(carry == 1) cur->next = new ListNode(1);\n" +
    "        return dummy->next;\n" +
    "    }\n" +
    "};"
);

const originalValue = ref("");

/**
 * markdown 编辑器内容改变时触发
 * @param val
 */
const handleMdChange = (val: string) => {
  mdValue.value = val;
};

/**
 * monaco 编辑器内容改变时触发
 * @param val
 */
const handleCodeChange = (val: string) => {
  codeValue.value = val;
};

/**
 * monaco diff 编辑器内容改变时触发
 * @param val
 */
const handleDiffCodeChange = (val: string) => {
  originalValue.value = val;
};
</script>
