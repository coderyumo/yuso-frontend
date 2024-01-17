<template>
  <a-list
    :data-source="props.videoList"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    item-layout="horizontal"
  >
    <template #renderItem="{ item }">
      <a-list-item>
        <!-- 使用 <a> 标签包装 <a-card>，并设置 href 属性 -->
        <a :href="item.videoUrl" target="_blank">
          <a-card hoverable style="width: 200px; height: 200px">
            <template #cover>
              <img :alt="item.title" src="../assets/gege.jpg" />
            </template>
            <a-card-meta :title="item.title" />
          </a-card>
        </a>
      </a-list-item>
    </template>
  </a-list>
</template>

<script lang="ts" setup>
import { withDefaults, defineProps } from "vue";

interface Props {
  videoList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  videoList: () => [],
});
</script>

<style scoped></style>
