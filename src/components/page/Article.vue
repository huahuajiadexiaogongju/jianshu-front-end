<template>
    <div>
      <div class="row out-set" v-for="article in articleList" :key="article.id" >
        <b-col  cols="8">
          <p style="font-size: 18px;font-weight: bold;color: #333;padding-top: 6%">{{article.title}}</p>
          <p style="color: grey;font-size: 12px;color: gray;letter-spacing: 1px">{{article.introduction}}</p>
          <div class="line">
            <img  :src="article.icon1" class="icon1">
            <p class="amount-text">{{article.amount1}}</p>
            <img  :src="article.icon2" class="icon2">
            <p class="amount-text">{{article.amount2}}</p>
            <img  :src="article.icon3" class="icon3">
            <p class="amount-text">{{article.amount3}}</p>
            <p class="amount-text time-location">{{article.time}}</p>
          </div>


        </b-col>
        <b-col  cols="4" style="margin-top:5%">
          <img :src="article.url" class="picture">
        </b-col>
      </div>

    </div>
</template>

<script>
    export default {
        name: "Article",
      data() {
        return {
          slide: 0,
          sliding: null,
          articleList: [
            {
              "id": 1,
              "title": "时间的灰烬‖第二章 一息尚存 ",
              "introduction": "从公交车上下来，再过一个宽阔的路口，即到羊角镇小学的门边。一扇锈迹斑斑的铁门里面有一幢三层白色瓷砖的小楼，阳台则是天蓝色瓷砖，前面一片青灰水...",
              "url": "https://upload-images.jianshu.io/upload_images/2558050-ef8d9f002052927f.jpg",
              "icon1":"http://p88kzenjw.bkt.clouddn.com/eye1.png",
              "amount1":78,
              "icon2":"http://p88kzenjw.bkt.clouddn.com/message.png",
              "amount2":13,
              "icon3":"http://p88kzenjw.bkt.clouddn.com/like.png",
              "amount3":56,
              "time":"前天 00:24"
            },
            {
              "id": 2,
              "title": "时间的灰烬‖第一章 无眠 4",
              "introduction": "从公交车上下来，再过一个宽阔的路口，即到羊角镇小学的门边。一扇锈迹斑斑的铁门里面有一幢三层白色瓷砖的小楼，阳台则是天蓝色瓷砖，前面一片青灰水...",
              "url": "https://upload-images.jianshu.io/upload_images/2558050-743ed993b590351c.jpg",
              "icon1":"http://p88kzenjw.bkt.clouddn.com/eye1.png",
              "amount1":78,
              "icon2":"http://p88kzenjw.bkt.clouddn.com/message.png",
              "amount2":13,
              "icon3":"http://p88kzenjw.bkt.clouddn.com/like.png",
              "amount3":56,
              "time":"10.07 23:41"
            },
            {
              "id": 3,
              "title": "《江湖儿女》：所谓江湖，也只是个人选择",
              "introduction": "从公交车上下来，再过一个宽阔的路口，即到羊角镇小学的门边。一扇锈迹斑斑的铁门里面有一幢三层白色瓷砖的小楼，阳台则是天蓝色瓷砖，前面一片青灰水...",
              "url": "https://upload-images.jianshu.io/upload_images/2558050-db4e6411857b830e.jpg",
              "icon1":"http://p88kzenjw.bkt.clouddn.com/eye1.png",
              "amount1":78,
              "icon2":"http://p88kzenjw.bkt.clouddn.com/message.png",
              "amount2":13,
              "icon3":"http://p88kzenjw.bkt.clouddn.com/like.png",
              "amount3":56,
              "time":"前天 00:24"
            },
            {
              "id": 4,
              "title": "小说‖猫，女孩与孔明灯",
              "introduction": " 猫是一只流浪在学校草坪上的猫，它每天无所事事地游荡在那一片绿意葱葱的草地上，累了就找个舒适地方躺下睡觉，饿了就去食堂里蹭一些残羹冷炙，晴天...",
              "url": "https://upload-images.jianshu.io/upload_images/2558050-db76ad4af2de7691.jpg",
              "icon1":"http://p88kzenjw.bkt.clouddn.com/eye1.png",
              "amount1":100,
              "icon2":"http://p88kzenjw.bkt.clouddn.com/message.png",
              "amount2":5,
              "icon3":"http://p88kzenjw.bkt.clouddn.com/like.png",
              "amount3":0,
              "time":"06.06 00:47"
            },


          ]
        }
      }
    }
</script>

<style scoped>
  .picture{
    width:128px;
    height: 100px;
  }
  .icon1{
    width: 15px;
    height: 14px;
  }
  .icon2{
    width: 15px;
    height: 14px;
    margin-left: 5%;
  }
  .icon3{
    width: 16px;
    height: 15px;
    margin-left: 4%;
  }
  .amount-text{
    font-size: 12px;
    color: gray;
    margin-left: 1%;
    margin-top: -1px;
  }

  .line{
    display: flex;
  }
  .time-location{
    margin-left: 6%;
  }
  .out-set{
   border-bottom: 1px solid #f0f0f0;
    padding-bottom: 1%

  }

</style>
