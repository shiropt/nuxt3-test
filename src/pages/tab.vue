<script setup lang="ts">
const Edit = resolveComponent("TabContentEdit");
const Home = resolveComponent("TabContentHome");
const Detail = resolveComponent("TabContentDetail");
const currentTab = ref(Home);
const selectTab = (value: "HOME" | "DETAIL" | "EDIT") => {
  if (value === "HOME") {
    currentTab.value = Home;
  }
  if (value === "DETAIL") {
    currentTab.value = Detail;
  }
  if (value === "EDIT") {
    currentTab.value = Edit;
  }
};
</script>
<template>
  <div>
    <div class="tab-wrap">
      <div class="tab-head-wrap">
        <div @click="selectTab('HOME')">Home</div>
        <div @click="selectTab('DETAIL')">Detail</div>
        <div @click="selectTab('EDIT')">Edit</div>
      </div>
      <keep-alive>
        <component :is="currentTab" />
      </keep-alive>
    </div>
  </div>
</template>
<style>
.tab-head-wrap {
  display: flex;
  justify-content: space-around;
}
.tab-head-wrap > div {
  background: rgb(240, 238, 238);
  border: 1px solid rgb(146, 140, 140);
  width: 100%;
  height: 40px;
  line-height: 40px;
  text-align: center;
  cursor: pointer;
}
.tab-head-wrap > div:hover {
  opacity: 0.7;
}
</style>
