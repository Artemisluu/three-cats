<template>
  <div class="tags">
    <div class="icon-list">
      <div
          v-for="item in items"
          :key="item"
          @click="toggle(item)"
          :class="['icon-list-item', {selected:selectedTags.indexOf(item)>=0}]"
      >
        <Icon :name="item"/>
        {{ item }}
      </div>
    </div>
  </div>

</template>

<script lang="ts">

import Vue from 'vue';
import {Component} from 'vue-property-decorator';

@Component
export default class Tags extends Vue {
  items: string[] = [
    '保险',
    '医疗',
    '宠物',
    '家居',
    '家电',
    '服装',
    '机票',
    '游戏',
    '生鲜',
    '电影',
    '维修',
    '美妆',
    '美食',
    '酒店',
  ];
  selectedTags: string[] = [];

  toggle(tag: string) {
    const index = this.selectedTags.indexOf(tag);
    if (index >= 0) {
      this.selectedTags.splice(index, 1);
    } else {
      this.selectedTags.push(tag);
    }
  }
}


</script>

<style lang="scss" scoped>

.tags {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column-reverse;
  padding: 25px;
  flex-grow: 1;

  .icon-list {
    font-size: 14px;
    flex-grow: 1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;


    .icon-list-item {
      width: 44px;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      align-items: center;

      &.selected {
        color: #FF6C39;

        .icon {
          fill: #FF6C39;
        }
      }

      .icon {
        width: 36px;
        height: 36px;
      }
    }


  }

}


</style>