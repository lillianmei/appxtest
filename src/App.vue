<template>
  <el-header style="text-align: right; font-size: 12px">
    <el-row>
      <el-col :span="12" class="header-left">
        <div @click="collapse">
          <img src="@/assets/image/menu.svg" alt="logo" />
        </div>
        <div class="logo">
          <img src="@/assets/image/logo.svg" alt="logo" />
        </div>
        <div class="search">
          <el-input class="w-50 m-2" size="large" placeholder="Search here.." :suffix-icon="Search" />
          <el-select placeholder="By All" style="width: 115px; margin-left: 8px">
            <el-option label="By All" value="1" />
            <el-option label="By Station" value="2" />
            <el-option label="By Country" value="3" />
          </el-select>
        </div>
      </el-col>
      <el-col :span="12" class="header__right">
        <div class="weather">
          <div class="weather__icon"></div>
          <span>09:54 am</span>
        </div>
        <div class="country-select">
          <el-select placeholder="Antananarivo" style="width: 130px; margin-left: 8px">
            <el-option label="Antananarivo" value="1" />
            <el-option label="HongKong" value="2" />
            <el-option label="Tokyo" value="3" />
          </el-select>
        </div>
        <div class="setting"></div>
        <div class="bell"></div>
        <div class="avatar">
          <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png" />
        </div>
      </el-col>
    </el-row>
  </el-header>
  <el-container class="layout-container-demo">
    <el-container>
      <el-aside class="aside-menu" :class="{ 'is-close': !isCollapse }">
        <el-scrollbar>
          <el-menu>
            <el-sub-menu index="1">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__home"></div>
                  <span>Home General</span>
                </div>
              </template>
              <el-menu-item-group>
                <router-link to="/">
                  <el-menu-item index="1-1">Option 1</el-menu-item>
                </router-link>
                <router-link to="/item">
                  <el-menu-item index="1-2" class="menu-group-title">Option 2</el-menu-item>
                </router-link>
                <el-menu-item index="1-3" class="menu-group-title">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="1-4">
                <template #title>Option4</template>
                <el-menu-item index="1-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
            <el-sub-menu index="2">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__sale"></div>
                  <span>Marketing & Sales</span>
                </div>
              </template>
              <el-menu-item-group>
                <el-menu-item index="2-1">Option 1</el-menu-item>
                <el-menu-item index="2-2">Option 2</el-menu-item>
                <el-menu-item index="2-3">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="2-4">
                <template #title>Option 4</template>
                <el-menu-item index="2-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
            <el-sub-menu index="3">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__customer"></div>
                  <span>Customer Service & <br> Operation</span>
                </div>
              </template>
              <el-menu-item-group>
                <el-menu-item index="3-1">Option 1</el-menu-item>
                <el-menu-item index="3-2">Option 2</el-menu-item>
                <el-menu-item index="3-3">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="3-4">
                <template #title>Option 4</template>
                <el-menu-item index="3-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
            <el-sub-menu index="4">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__car"></div>
                  <span>Carrier Management</span>
                </div>
              </template>
              <el-menu-item-group>
                <el-menu-item index="4-1">Option 1</el-menu-item>
                <el-menu-item index="4-2">Option 2</el-menu-item>
                <el-menu-item index="4-3">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="4-4">
                <template #title>Option 4</template>
                <el-menu-item index="4-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
            <el-sub-menu index="5">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__finance"></div>
                  <span>Finance & Accounting</span>
                </div>
              </template>
              <el-menu-item-group>
                <el-menu-item index="5-1">Option 1</el-menu-item>
                <el-menu-item index="5-2">Option 2</el-menu-item>
                <el-menu-item index="5-3">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="5-4">
                <template #title>Option 4</template>
                <el-menu-item index="6-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
            <el-sub-menu index="6">
              <template #title>
                <div class="aside-menu__title">
                  <div class="menu-icon menu-icon__hr"></div>
                  <span>HR Development & <br> Organization Setup</span>
                </div>
              </template>
              <el-menu-item-group>
                <el-menu-item index="6-1">Option 1</el-menu-item>
                <el-menu-item index="6-2">Option 2</el-menu-item>
                <el-menu-item index="6-3">Option 3</el-menu-item>
              </el-menu-item-group>
              <el-sub-menu index="6-4">
                <template #title>Option 4</template>
                <el-menu-item index="6-4-1" class="menu-group-sub-menu">Option 4-1</el-menu-item>
              </el-sub-menu>
            </el-sub-menu>
          </el-menu>
        </el-scrollbar>
      </el-aside>
      <el-main>
        <breadcrumb />
        <search />
        <pagination />
        <RouterView />
      </el-main>
    </el-container>
  </el-container>
</template>

<script setup>
import { ref } from 'vue'
import { Search } from '@element-plus/icons-vue'
import breadcrumb from '@/components/Breadcrumb.vue'
import search from '@/components/Search.vue'

components: {
  breadcrumb
  search
}
const isCollapse = ref(true)

const collapse = () => {
  isCollapse.value = !isCollapse.value
}
</script>

<style lang="scss">
header {
  max-height: 100vh;

  .header-left {
    display: flex;
    align-items: center;
    justify-content: flex-start;

    .logo {
      img {
        margin: 0 34px 0 52px;
      }
    }

    .search {
      display: flex;
    }
  }

  .header__right {
    display: flex;
    align-items: center;
    justify-content: flex-end;

    >div {
      margin-right: 16px;
    }

    .country-select {
      .el-input {
        font-size: 18px;
        --el-input-bg-color: #f5f5f5;
        --el-input-border-color: #f5f5f5;
        --el-border-color-hover: #f5f5f5;
      }
    }

    .weather {
      display: flex;
      align-items: center;

      span {
        font-size: 18px;
        font-weight: 600;
        color: #374557;
      }

      &::before {
        width: 20px;
        height: 20px;
        content: url('@/assets/image/weather-icon.svg');
        margin-right:10px;
      }
    }

    .setting {
      width: 25px;
      height: 25px;
      margin: 0 20px;
      content: url('@/assets/image/setting-icon.svg');
    }

    .bell {
      width: 25px;
      height: 25px;
      margin: 0 20px;
      content: url('@/assets/image/bell-icon.svg');
    }

    .avatar {}
  }
}

.aside-menu {
  width: 300px;
  transition: all .3s ease;

  &__title {
    width: 100%;
    display: flex;
    flex-wrap: nowrap;
    position: relative;

    span {
      position: absolute;
      left: 32px;
    }
  }

  &.is-close {
    width: 60px;

    li {
      pointer-events: none;
    }

    .aside-menu__title {
      display: inline-block;

      .menu-icon {
        margin-right: 0;
      }

      span {
        display: none;
      }
    }
  }

  .el-sub-menu__title {
    span {
      font-weight: 700;
    }
  }
}

.menu-icon {
  width: 20px;
  height: 20px;
  margin-right: 12px;

  &__home {
    background-image: url(@/assets/image/menuIcon-home.svg);
    background-repeat: no-repeat;
  }

  &__customer {
    background-image: url(@/assets/image/menuIcon-customer.svg);
    background-repeat: no-repeat;
  }

  &__car {
    background-image: url(@/assets/image/menuIcon-car.svg);
    background-repeat: no-repeat;
  }

  &__finance {
    background-image: url(@/assets/image/menuIcon-finance.svg);
    background-repeat: no-repeat;
  }

  &__hr {
    background-image: url(@/assets/image/menuIcon-hr.svg);
    background-repeat: no-repeat;
  }

  &__sale {
    background-image: url(@/assets/image/menuIcon-sale.svg);
    background-repeat: no-repeat;
  }
}

.el-row {
  width: 100%;
}

.el-input-group__append button.el-button {
  background-color: #fff;
  border: 1px solid #737791;
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
  border-left: 0;
  height: 48px;
}

.menu-group-sub-menu {
  font-weight: 500;
  color: #565867;
}

.el-menu {
  border-right: none;
}

.el-main {
  padding: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding: 0 16px;
  }
}</style>
