<template>
  <div class="list-topic">
    <div class="list-topic__search">
      <a-input placeholder="Nhập tên tên giáo viên ..." />
      <a-button type="primary">Search</a-button>
      <a-button type="primary" @click="handleForm">Đăng ký đề tài</a-button>
    </div>
    <a-table :columns="columns" :data-source="data">
      <template #bodyCell="{ column, text }">
        <template v-if="column.dataIndex === 'name'">
          <a>{{ text }}</a>
        </template>
      </template>
    </a-table>
    <modal-form-register v-if="isOpen" @close="closeModal" />
  </div>
</template>
<script setup>
definePageMeta({
  layout: "layout",
});
const isOpen = ref(false);
const columns = [
  {
    title: "MGV",
    dataIndex: "name",
    key: "name",
    width: 80,
  },
  {
    title: "Tên giáo viên hướng dẫn",
    dataIndex: "age",
    key: "age",
  },
  {
    title: "Đề tài",
    dataIndex: "address",
    key: "address 1",
    ellipsis: true,
  },
  {
    title: "Số lượng SV/đề tài",
    dataIndex: "address",
    key: "address 2",
    ellipsis: true,
  },
  {
    title: "Đã đăng ký đề tài",
    dataIndex: "address",
    key: "address 3",
    ellipsis: true,
  },
  {
    title: "Đã được đồng ý",
    dataIndex: "address",
    key: "address 4",
    ellipsis: true,
  },
];
const data = [
  {
    key: "1",
    name: "MT2",
    age: 32,
    address: "New York No. 1 Lake Park, New York No. 1 Lake Park",
    tags: ["nice", "developer"],
  },
  {
    key: "2",
    name: "MV3",
    age: 42,
    address: "London No. 2 Lake Park, London No. 2 Lake Park",
    tags: ["loser"],
  },
  {
    key: "3",
    name: "DC4",
    age: 32,
    address: "Sidney No. 1 Lake Park, Sidney No. 1 Lake Park",
    tags: ["cool", "teacher"],
  },
];
const handleForm = () => {
  isOpen.value = true;
  console.log(123);
};
const closeModal = () => {
  isOpen.value = false;
};
</script>

<style lang="scss" scoped>
@import "./index.scss";
</style>
