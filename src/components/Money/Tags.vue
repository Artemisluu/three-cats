<template>
  <div class="tags">
    <div class="icon-list">
      <div v-for="item in items" :key="item" class="icon-list-item">
        <Icon :name="item"/>
        {{ item }}
      </div>
    </div>
  </div>

</template>

<script lang="ts">

export default {
  name: 'Tags',
  data() {
    return {
      items: [
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
      ]
    };
  }
};
</script>

<style lang="scss" scoped>

.tags {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column-reverse;
  padding: 25px;

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

      .icon {
        width: 36px;
        height: 36px;
      }
    }


  }

}


</style>