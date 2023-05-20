<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.videoList"
  >
    <template #renderItem="{ item }">
      <a-list-item>
        <a :href="item.arcurl">
          <a-card>
            <template #cover>
              <img :src="item.pic" referrerpolicy="no-referrer" />
            </template>
            <a :href="item.arcurl">
              <a-card-meta :title="item.author" />
            </a>
          </a-card>
        </a>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from "vue";

interface Props {
  videoList: any[];
}

const props = withDefaults(defineProps<Props>(), {
  videoList: () => [],
});
</script>

<style scoped></style>
