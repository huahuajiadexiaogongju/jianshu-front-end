<template>
  <div>
    <b-row>
      <b-col cols="8">
        <b-media vertical-align="center" class="article-box">
          <img :src="topic.topicUrl" class="avatar"/>
          <p class="name">{{topic.topicName}}</p>
          <p class="abstract">
            <span class="count">收藏了{{topic.articleCount}}篇文章·{{topic.fans}}关注</span>
          </p>
        </b-media>
        <div class="button">
          <b-button variant="outline-success">投稿</b-button>
          <b-button class="focuss" variant="success">+关注</b-button>
        </div>

        <div class="main">
                <a v-for="article in topic.articleList" :key="article.id" >
                  <div class="main1">
                    <b-row>
                      <b-col cols="9" class="main2">
                        <div class="title">{{article.title}}</div>
                        <div class="summary">{{article.summary}}</div>
                        <div class="nickname">{{article.nickname}}</div>
                        <div class="main3">
                          <img class="comment" src="../../../static/img/comments.png"/>
                          <div class="comments">{{article.comments}}</div>
                          <img class="like" src="../../../static/img/likes.png">
                          <div class="likes">{{article.likes}}</div>
                        </div>
                      </b-col>
                      <b-col col="3">
                        <div class="main4">
                          <img class="thumbnail" :src="article.thumbnail"/>
                        </div>
                      </b-col>
                    </b-row>
                  </div>
                </a>
        </div>
      </b-col>
      <b-col cols="4">
        <div class="main5">
          <p class="notice">专题公告</p>
          <p class="description">{{topic.description}}</p>
        </div>
        <div class="share">
          <p class="share1">分享到</p>
          <div class="icon">
            <b-img class="pic1" src="http://p88kzenjw.bkt.clouddn.com/weibo.png" />
            <b-img class="pic2" src="http://p88kzenjw.bkt.clouddn.com/wechat1.png" />
            <b-img class="pic2" src="http://p88kzenjw.bkt.clouddn.com/more.png" />
          </div>
        </div>
      </b-col>
    </b-row>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        id: this.$route.params.id,
        topic: {},
        articleList: [],
        fansList:[]
      }
    },
    activated() {
      this.id = this.$route.params.id;
      console.log(this.id);
      if (this.id == 1) {
        var t = {
          "id": 1,
          "topicName": "摄影",
          "topicUrl": "https://upload.jianshu.io/collections/images/83/1.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/64/h/64",
          "summary": "读书读书读书读书读书读书读书读书",
          "articleCount": 49535,
          "fans": 1601,
          "description":"欢迎关注公众号简宝玉( 公众号ID : jianshu4321 )后台回复“指南”获取玩转简书绝密珍贵资料汇总；有问题，找宝玉。简宝玉同志会专程为你答疑解惑关于简书的一切。 \n" +
          "生活本无趣 \n" +
          "光影挽留年 \n" +
          "用图片 说故事 \n" +
          "记录生活 记录美好\n" +
          "\n" +
          "每个人都是独特的艺术家 \n" +
          "用快门捕捉你双眼所见，心有所感的一切\n" +
          "\n" +
          "专题投稿，首页推荐，摄影爱好交流详见： \n" +
          "https://www.jianshu.com/p/e330ab6b2f65\n" +
          "\n" +
          "专题主编:小久英 \n" +
          "https://www.jianshu.com/u/aa73c6c31eb1",
          "creator":"简书",
          "articleList":[
            {
              "id":1,
              "title":"碎碎念",
              "summary":"莫名就喜欢这张照片，不是因为图片上的人，那是个算不上路人甲的路人。为什么喜欢呢？说不出来。 有时语言的贫瘠无法表达眼睛看到的感受。 这株小草叫益...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/5574423-c954d0862f6741b8.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":2,
              "nickname":"孔雀东南飞飞",
              "comments":1234,
              "likes":12
            },
            {
              "id":2,
              "title":"长相思.重阳思归",
              "summary":"忆重阳，又重阳。丹叶黄花秋气凉，脚踮娘唤郎。 雁两行，泪两行。暮帆只影归意长，茱剪儿梦娘。",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/8819508-f2d0d3f4d98e5b48.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":3,
              "nickname":"三生有幸之遇见",
              "comments":8,
              "likes":8,
            },
            {
              "id":3,
              "title":"银杏秋姿",
              "summary":"摄影｜陵子 当我们变老的时候， 这世界依然年轻貌美， 一切都是循环往复， 犹如这银杏叶， 秋去春又回， 每一场轮回， 都在声色里进行着……",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/7611248-d75d956144d750e0.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":4,
              "nickname":"陵子心语",
              "comments":2,
              "likes":7,
            },
            {
              "id":4,
              "title":"闲话文件——恰当的量，合适的度",
              "summary":"【整理旧文字，记于17年8月某日】 水至清，则无鱼；水浑到一定程度，也会把鱼呛死。度的问题，量的问题。 某日，与一个老板同学哈酒，喝到酣畅处，与...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/12334394-1a5497808015469c.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":5,
              "nickname":"闲述老魏",
              "comments":2,
              "likes":3,
            },
            {
              "id":5,
              "title":"行走上海 | 虹口区历史建筑",
              "summary":"此行的初衷大概是寻找这个 乍浦路260号景林庐上海乍浦路、昆山路的景林庐，建于1923年，典型的上海近代时期外廊式建筑，略有英国安妮时期建筑的风...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/14493696-6b5ba2cd1ec19d1d?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":6,
              "nickname":"Clsea",
              "comments":2,
              "likes":3,
            },
            {
              "id":6,
              "title":"在雨中漫步大理",
              "summary":"独自旅行的第二站——大理 想要带你去浪漫的土耳其，然后一起去东京和巴黎，，，，我们一起去上海和北京，还有云南的大理，保留着回忆，这样才有意义。我...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/9926098-8d18fcd3c7ed16ec.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":7,
              "nickname":"逐野之鹿",
              "comments":2,
              "likes":4,
            },
            {
              "id":7,
              "title":"再见，Grafton",
              "summary":"明天一早我们就将乘坐火车离开Grafton，行程总时长10h19m。特地选了白天的班次，因为大宥和我都喜欢在列车上慢慢的穿越风景。这趟旅程算是把...",
              "thumbnail":"https://upload-images.jianshu.io/upload_images/8908528-904f625f553cc6d9.jpg?imageMogr2/auto-orient/strip|imageView2/1/w/300/h/240",
              "authorId":8,
              "nickname":"溜小二",
              "comments":0,
              "likes":2,
            },
          ],
          "fansList":[
            {
              "authorId":3,
              "avatar":"11.png"
            }
          ]
        };
        this.topic = t;
      } else {
        this.topic = {};
      }
    },
    computed: function () {
      return this.topic;
    }
  }
</script>

<style scoped>
  .avatar{
    margin-left: 10%;
    width: 12%;
    margin-top: 5%;
  }
  .name{
    margin-top: -11%;
    margin-left: 24%;
    font-size: 21px;
    font-weight: bolder;
  }
  .abstract{
    margin-top: -1%;
    margin-left: 24%;
  }
  .count{
    color: gray;
  }
  .button{
    margin-left: 80%;
    margin-top: -10%;
  }
  .focuss{
    margin-left: 5%;
  }
  .main{
    margin-top: 8%;
    margin-left: 9%;
  }
  .main1{
    border-bottom: 1px #f0f0f0 solid;
    border-top: 1px #f0f0f0 solid;
  }
  .main2{
    margin-top: 2%;
  }
  .title{
    font-size: 19px;
    font-weight: bolder;
  }
  .summary{
    color: gray;
    font-size: 13px;
    margin-top: 2%;
  }
  .nickname{
    font-size: 13px;
    color: gray;
    margin-top: 2%;
  }
  .main3{
    margin-left: 19%;
    margin-top: -4.5%;
  }
  .comment{
    width: 4%;
  }
  .comments{
    margin-top: -5%;
    margin-left: 5%;
    font-size: 13px;
    color: gray;
  }
  .like{
    width: 4%;
    margin-top: -12%;
    margin-left: 15%;
  }
  .likes{
    margin-top: -11%;
    margin-left: 19%;
    font-size: 13px;
    color: gray;
  }
  .main4{
    margin-top: 15%;
    margin-bottom: 12%;
  }
  .thumbnail{
    width: 93%;
  }
  .main5{
    margin-top: 8%;
    border-bottom: 1px solid #f0f0f0;
  }
  .notice{
    color: gray;
  }
  .description{
    font-size: 15px;
    margin-right: 12%;
  }
  .share{
    margin-top: 5%;
    border-bottom: 1px solid #f0f0f0;
  }
  .icon{
    margin-left: 20%;
  }
  .share1{
    color: gray;
  }
  .pic1{
    margin-top: -30%;
    width: 8%;
  }
  .pic2{
    margin-top: -30%;
    width: 8%;
    margin-left: 5%;
  }


</style>













<!--<template>-->

<!--</template>-->

<!--<script>-->
    <!--export default {-->
        <!--name: "Collection",-->
      <!--data(){-->
          <!--return{-->
            <!--id:this.$route.params.id,-->
            <!--topic:{},-->
            <!--articleList:[],-->
            <!--fansList:[]-->
          <!--}-->
      <!--},-->
      <!--activated(){-->
          <!--this.id = this.$route.params.id-->
      <!--}-->
    <!--}-->
<!--</script>-->

<!--<style scoped>-->

<!--</style>-->
