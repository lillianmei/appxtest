<template>
  <pagination />
  <el-row class="content" v-for="(item, index) in contentItem.data" :key="item">
    <el-col :span="19" class="content__item">
      <div class="tag" @click="collect(index)"></div>
      <div class="news-item">
        <p>{{ item.title }}</p>
        <div class="news-item-info">
          <div class="like">
            <span>{{ item.like }} Likes</span>
          </div>
          <div class="comment">
            <span>{{ item.comment }} comments</span>
          </div>
          <div class="reply">
            <span>{{ item.reply }} shares</span>
          </div>
        </div>
      </div>
    </el-col>
    <el-col :span="5" class="content__note">
      <div class="type">{{ item.type }}</div>
      <div class="time">{{ item.date }}</div>
    </el-col>
  </el-row>
</template>


<script setup>
import { reactive, ref } from 'vue'
import pagination from '@/components/Pagination.vue'

components: {
  pagination
}

let contentItem = reactive({
  data: [
    { title: "1Lorem ipsum dolor sit amet consectetur,cing elit. Eius....", like: 10, comment: 3, reply: 5, type: 'News', date: 'Dec 19,2022' },
    { title: "2Lorem ipsum dolor sit amet consectetur,cing elit. Eius....", like: 10, comment: 3, reply: 5, type: 'News', date: 'Dec 19,2022' },
    { title: "3Lorem ipsum dolor sit amet consectetur,cing elit. Eius....", like: 10, comment: 3, reply: 5, type: 'News', date: 'Dec 19,2022' },
    { title: "4Lorem ipsum dolor sit amet consectetur,cing elit. Eius....", like: 10, comment: 3, reply: 5, type: 'News', date: 'Dec 19,2022' },
    { title: "5Lorem ipsum dolor sit amet consectetur,cing elit. Eius....", like: 10, comment: 3, reply: 5, type: 'News', date: 'Dec 19,2022' },
  ]
})

const collect = (index) => {
  console.log(index)
  for (let i = 0; i < contentItem.data.length; i++) {
    if (index == i) {
      contentItem.data.splice(i, 1)
    }
  }
}

</script>

<style scoped lang="scss">
.content {
  padding: 16px;
  border: 1px solid #ddd;
  border-bottom: none;
  background-color: #fff;

  &:last-of-type {
    border-bottom: 1px solid #ddd;
    ;
  }
}

.content__item {
  display: flex;
  align-items: flex-start;

  .tag {
    cursor: pointer;
    margin-top: 5px;
    width: 13px;
    height: 18px;
    background: url('@/assets/image/tag-icon.svg');
    background-size: cover;
    margin-right: 20px;
  }

  .news-item {
    p {
      font-weight: 600;
    }

    .news-item-info {
      display: flex;
      margin-top: 20px;

      >div {
        margin-right: 20px;
        display: flex;
        span{
          color: #737791;
        }

        &.like {
          &::before {
            content: url('@/assets/image/like-icon.svg');
            margin-right: 8px;
            padding-top: 3px;
          }
        }

        &.comment {
          &::before {
            content: url('@/assets/image/comment-icon.svg');
            margin-right: 8px;
            padding-top: 3px;
          }
        }

        &.reply {
          &::before {
            content: url('@/assets/image/reply-icon.svg');
            margin-right: 8px;
            padding-top: 3px;
          }

        }
      }
    }
  }
}

.content__note {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  justify-content: center;
  font-size: .85rem;

  .type {
    padding: 4px 12px;
    background-color: #EDEDED;
    border-radius: 30px;
    color: #11263C;
  }

  .time {
    font-size: .8rem;
    color: #737791;
    margin-top: 8px;
  }
}
</style>