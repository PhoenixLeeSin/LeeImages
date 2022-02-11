/**
 * 选择或者编辑定位
 */
<template>
    <view class="wrapper">
       <!-- 导航栏 -->
       <navbar @backClick="handleBack" bgColor="#fff">
        <view slot="center" class="nav-center">
          <text>选择收货地址</text>
        </view>
        <view slot="right" class="nav-right">
           <text>管理</text>
        </view>
       </navbar>
       <!-- 滚动视图容器 -->
       <gxscroll class="container">
         <view slot="scrollcontent">
          <view class="search">
             <view class="search-left">
               <view class="search-left-title">青岛市</view>
               <view class="search-left-content">
                 <u-icon name="search" size="32rpx" color="#757575"></u-icon>
                 <input class="input" placeholder="小区/写字楼/学校等"></input>
               </view>
             </view>
             <view class="search-right">搜索</view>
           </view>
          <!-- 当前定位 -->
          <view class="currentloc">
            <view class="currentloc-title">当前定位</view>
            <view class="currentloc-pos">
              <view class="loc">北京</view>
              <view class="reloc">
                <u-icon name="dingwei" custom-prefix="custom-icon" size="30" color="#4F7DFF"></u-icon>
                <view class="reloc-title">重新定位</view>
              </view>
            </view>
          </view>
        </view>
       </gxscroll>
    </view>
</template>

<script>
  export default {
    data() {
      return {
        
      }
    },
    methods: {
      handleBack() {
        uni.navigateBack()
      }
    }
  }
</script>

<style lang="scss" scoped>
@import '../../style/mixin.scss';
.wrapper {
  display: flex;
  flex-direction: column;
  flex: 1;
  width: 100%;
  .nav-center {
    font-size: 36rpx;
    color: $mk-base-textcolor;
  }
  .nav-right {
    font-size: 30rpx;
    color: $mk-base-textcolor;
  }
  .container {
    background-color: #F4F6F9;
    padding: 22rpx 30rpx 0 30rpx ;
  }
  .search {
      display: flex;
      align-items: center;
      &-left {
        display: flex;
        align-items: center;
        box-sizing: border-box;
        height: 64rpx;
        line-height: 64rpx;
        padding-left: 36rpx;
        background-color: #F8F8F8;
        border-radius: 40rpx;
        &-title {
          font-weight: 500;
          font-size: 28rpx;
          color: #282828;
        }
        &-content {
          display: flex;
          padding-left: 34rpx;
          align-items: center;
          margin: 12rpx 44rpx 0;
          height: 40rpx;
          border-left: 1px solid #757575;
          .input {
            padding-left: 20rpx;
            font-size: 28rpx;
            color: #282828;
            font-weight: 500;
            /deep/ .input-placeholder {
              margin-left: 28rpx;
              font-size: 24rpx;
              color: #757575;
              font-weight: 500;
            }
          }
        }
      }
      &-right {
          font-weight: 500;
          font-size: 28rpx;
          color: #282828;
      }
    }
  .currentloc {
    display: flex;
    flex-direction: column;
    padding: 20rpx 0 0 0;
    &-title {
      color: $mk-base-middletextcolor;
      font-size: 24rpx;
      margin-bottom: 20rpx;
    }
    &-pos {
      display: flex;
      justify-content: space-between;
      align-items: center;
      .loc {
        flex: 1;
        font-size: 30rpx;
        color: $mk-base-textcolor;
      }
      .reloc {
        display: flex;
      }
    }
  }  
}    
</style>
