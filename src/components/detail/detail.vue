<template>
  <div class="detail" >
    <div class="back-wrapper">
      <Back :backText="backText" :centerText="centerText" @go-back="_goBack" ></Back>
    </div>
    <div class="content-wrapper" ref="detail-content">
      <div class="content" >
        <div class="header border-1px">
          <span class="title">头像</span>
          <div class="img-wrapper ">
            <img :src="personDetail.img"/>
          </div>
        </div>
        <!-- 基本信息 -->
        <ul class="list-wrapper base">
          <li v-for="(item,key) in base" :key="key" class="list">
            <div class="title">{{item.key}}</div>
            <div class="value" v-if="item.value">
              <span class="text">{{item.value | noText}}</span>
            </div>
            <div @click="_showPerson" class="value" v-if="!item.value">
              <span class="icon-qrcore"></span>
            </div>
          </li>
        </ul>
        <Split></Split>
        <!-- 主要信息 -->
        <ul class="list-wrapper">
          <li v-for="(item,key) in main" :key="key" class="list">
            <div class="title">{{item.key}}</div>
            <div class="value">
              <span class="text">{{item.value | noText}}</span>
            </div>
          </li>
        </ul>
        <Split></Split>
        <!-- 额外信息 -->
        <ul class="list-wrapper">
          <li v-for="(item,key) in main" :key="key" class="list">
            <div class="title">{{item.key}}</div>
            <div class="value">
              <span class="text">{{item.value | noText}}</span>
            </div>
          </li>
        </ul>
        <!-- 按钮 -->
        <div class="export-wrapper">
          <div class="export-btn" @click="_exportCard">
            <span class="text">加入通讯录</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6" src="./detail.js"></script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "./detail.styl";
</style>
