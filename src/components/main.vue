<template>
  <section class="main">
    <div class="container clearfix">
      <section class="wrap-left fl">
        <section class="top clearfix" aos="fade-up">
          <section class="fl">
            <figure class="mask">
              <img src="../../static/images/top_left.jpg" alt class="big-pic imgscale" />
              <figcaption>不选“扶摇”直上的人生</figcaption>
            </figure>
          </section>
          <section class="fr">
            <figure class="mask">
              <img src="../../static/images/top_right1.jpg" alt class="small-pic imgscale" />
              <figcaption>大专生Jony lve</figcaption>
            </figure>
            <figure class="mask">
              <img src="../../static/images/top_right2.jpg" alt class="small-pic imgscale" />
              <figcaption>借鉴还是抄袭？小米们请有些理论自信</figcaption>
            </figure>
          </section>
        </section>
        <section class="content">
          <ul>
            <li v-for="(item, index) in list" :key="index" aos="fade-up">
              <figure class="fl">
                <img :src="item.img" alt class="imgscale" />
              </figure>
              <section class="fr">
                <a class="title">{{ item.title }}</a>
                <section class="clearfix">
                  <img class="avatar" :src="item.avatar" />
                  <span>{{ item.from }}</span>
                  <span>{{ item.time }}</span>
                  <span>
                    <img src="../../static/images/comment.png" alt />
                    {{ item.comnum }}
                  </span>
                  <span>
                    <img src="../../static/images/collect.png" alt />
                    {{ item.colnum }}
                  </span>
                </section>
                <p>{{ item.info }}</p>
                <a href class="tag">{{ item.tag }}</a>
              </section>
            </li>
          </ul>
        </section>
      </section>
      <section class="wrap-right fr">
        <section class="hours right-box">
          <h3 @click="toA">24小时</h3>
          <span class="more">查看全部</span>
          <section class="content">
            <ul>
              <li v-for="(item, index) in hoursList" :key="index">
                <section class="top clearfix">
                  <img :src="item.avatar" alt />
                  <p>
                    <span class="title">{{ item.title }}</span>
                    <span class="time">{{ item.time }}</span>
                  </p>
                </section>
                <p>{{ item.content }}</p>
              </li>
            </ul>
          </section>
        </section>
        <section class="create right-box">
          <h3>创新快车道</h3>
          <span class="more">全部</span>
          <section class="content">
            <ul>
              <li v-for="(item, index) in createList" :key="index">
                <figure>
                  <img :src="item.avatar" alt />
                </figure>
                <section>
                  <a>{{ item.title }}</a>
                  <p>{{ item.info }}</p>
                </section>
              </li>
            </ul>
          </section>
          <section class="apply">
            <span class="btn">立即报名，获得曝光机会</span>
            <ul>
              <li v-for="(item, index) in applyList" :key="index">{{ item }}</li>
            </ul>
          </section>
        </section>
        <section class="case right-box">
          <h3>深案例</h3>
          <span class="more">全部</span>
          <section class="content">
            <figure>
              <img src="../../static/images/case.jpg" alt class="imgscale" />
            </figure>
            <section>
              <a>西贝的控制与失控</a>
              <p>一位观察者告诉虎嗅，西贝管理在某些方面还有点“糙”</p>
            </section>
          </section>
          <section class="explain">全年30+篇 案例分析，复盘有代表性的创新公司，还原商业成功背后的魔鬼细节。</section>
        </section>
        <section class="hot right-box">
          <h3>热文</h3>
          <section class="content">
            <ul>
              <li v-for="(item, index) in hotList" :key="index">
                <figure>
                  <img :src="item.img" alt class="imgscale" />
                </figure>
                <a href>{{ item.title }}</a>
              </li>
            </ul>
          </section>
        </section>
      </section>
    </div>
  </section>
</template>

<script>
import $ from 'jquery'
export default {
  data() {
    return {
      list: [
        {
          id: 1,
          title: "合理用药目录杀伤的不仅是20种西药，中成药更逃不掉",
          img: require("../../static/images/list1.jpg"),
          time: "13分钟前",
          comnum: 0,
          colnum: 1,
          info: "最大的争议点在于，究竟什么样的药算是辅助用药",
          tag: "医疗健康",
          from: "八点健闻",
          avatar: require("../../static/images/from1.jpg")
        },
        {
          id: 2,
          title: "又一个央企巨无霸诞生",
          img: require("../../static/images/list2.jpg"),
          time: "45分钟前",
          comnum: 7,
          colnum: 2,
          info: "“中国神船”来了",
          tag: "企业服务",
          from: "侠客岛@",
          avatar: require("../../static/images/from2.jpg")
        },
        {
          id: 3,
          title: "被数据“绑架”的电子游戏",
          img: require("../../static/images/list3.jpg"),
          time: "53分钟前",
          comnum: 0,
          colnum: 1,
          info: "设计师们盯着图表的时间，慢慢超过了游戏本身",
          tag: "娱乐淘金",
          from: "游戏时光VGtime@",
          avatar: require("../../static/images/from3.jpg")
        },
        {
          id: 4,
          title: "董事长涉嫌猥亵女童，公司连夜切割自救",
          img: require("../../static/images/list4.jpg"),
          time: "1小时前",
          comnum: 5,
          colnum: 3,
          info: "85后儿子上位，230亿财富能保住多少？",
          tag: "金融地产",
          from: "每日经济新闻@",
          avatar: require("../../static/images/from4.jpg")
        },
        {
          id: 5,
          title: "李彦宏演讲被泼水：演讲时遇到意外情况该如何处理？",
          img: require("../../static/images/list5.jpg"),
          time: "1小时前",
          comnum: 2,
          colnum: 4,
          info: "要想了解一个人，最好的方式就是看他如何应对意外......",
          tag: "生活腔调",
          from: "贺佳",
          avatar: require("../../static/images/from5.jpg")
        },
        {
          id: 6,
          title: "游资爆炒中烟香港背后虚幻的预期",
          img: require("../../static/images/list6.jpg"),
          time: "1小时前",
          comnum: 10,
          colnum: 17,
          info:
            "暴力拉升中烟香港股票的，很有可能是在两高、公安即将严打前刀口舔血的内地游资",
          tag: "金融地产",
          from: "阿尔法工场",
          avatar: require("../../static/images/from6.jpg")
        },
        {
          id: 7,
          title: "苹果的AR眼镜",
          img: require("../../static/images/list7.jpg"),
          time: "1小时前",
          comnum: 6,
          colnum: 28,
          info:
            "暴力拉升中烟香港股票的，很有可能是在两高、公安即将严打前刀口舔血的内地游资",
          tag: "人工智能",
          from: "Rex陈正翔@",
          avatar: require("../../static/images/from7.jpg")
        },
        {
          id: 8,
          title: "怎样才是餐饮数字化的正确姿势？",
          img: require("../../static/images/list8.jpg"),
          time: "2小时前",
          comnum: 2,
          colnum: 28,
          info:
            "全链路数字化背后，阿里本地生活服务在一定程度上展示出了侵略性。",
          tag: "特别策划",
          from: "钱德虎",
          avatar: require("../../static/images/from8.jpg")
        },
        {
          id: 9,
          title: "做品牌年轻化，还是要做年轻人的品牌？",
          img: require("../../static/images/list9.jpg"),
          time: "7小时前",
          comnum: 5,
          colnum: 62,
          info: "年轻化是手段，而不是目的",
          tag: "生活腔调",
          from: "时趣",
          avatar: require("../../static/images/from9.jpg")
        },
        {
          id: 10,
          title: "新《蜘蛛侠》“黑”了我们所有人",
          img: require("../../static/images/list10.jpg"),
          time: "8小时前",
          comnum: 3,
          colnum: 10,
          info: "（含剧透）一部《蜘蛛侠》的续集竟然推翻了《蜘蛛侠》自己",
          tag: "娱乐淘金",
          from: "壹条电影@",
          avatar: require("../../static/images/from10.jpg")
        }
      ],
      hoursList: [
        {
          id: 1,
          title: "三星“帝国”",
          time: "12分钟前",
          avatar: require("../../static/images/hours1.jpg"),
          content:
            "澳大利亚竞争与消费者委员会以手机防水广告涉嫌误导为由起诉三星。"
        },
        {
          id: 2,
          title: "华为稳不稳",
          time: "56分钟前",
          avatar: require("../../static/images/hours2.jpg"),
          content:
            "俄罗斯媒体报道，俄最大分类信息网站Avito运营服务公司表示，在俄2019上半年最畅销手机排行榜上，华为手机跃升两名，排名第四。苹果手机在该平台上总销量中的占比上半年达到43.5%，三星为17.6%。销量排行榜的第三名是小米手机，占比8.7%。"
        },
        {
          id: 3,
          title: "读数",
          time: "1小时前",
          avatar: require("../../static/images/hours3.jpg"),
          content:
            "7月4日，从公安部交管局获悉：截至2019年6月，全国机动车保有量达3.4亿辆，其中汽车2.5亿辆；全国66个城市汽车保有量超过100万辆，北京、成都等11个城市超过300万辆。其中，全国新能源汽车保有量达344万辆，占汽车总量的1.37%，与去年同期相比，增加145万辆，增长72.85%。"
        },
        {
          id: 4,
          title: "这话我服",
          time: "1小时前",
          avatar: require("../../static/images/hours4.jpg"),
          content:
            "7月3日晚，在东方青创营青听学院，俞敏洪称创业不为上市，也不为自己发财，而是实现你心中某个梦想。新东方花了16年才上市，那时他已经40岁。虽说“出名要趁早”，但他觉得不算晚。"
        },
        {
          id: 5,
          title: "飞行圈",
          time: "1小时前",
          avatar: require("../../static/images/hours5.jpg"),
          content:
            "据CNBC消息，波音公司将拨款1亿美元来帮助在去年10月印尼狮航（Lion Air）和今年3月埃塞俄比亚航空空难中遇难的346名遇难者的家属。据悉，这1亿美元并不是波音在未来可能必须向遇难者家属支付赔偿的一部分。"
        },
        {
          id: 6,
          title: "小扎老铁了",
          time: "1小时前",
          avatar: require("../../static/images/hours6.jpeg"),
          content:
            "Facebook区块链组负责人大卫·马库斯在周三发表的一篇博文中写道，“Facebook不会控制这种加密货币及其网络。也不会控制为其提供支持的储备金。”“到‘天秤币’推出时，Facebook只会是100多个‘天秤币协会’成员中的一个，届时我们不会有任何特殊的权利或特权。”"
        },
        {
          id: 7,
          title: "侯宏剑桥杂思",
          time: "3小时前",
          avatar: require("../../static/images/hours7.jpg"),
          content:
            "何谓产业互联网生态共同体？就是各个层次生态的嵌套和竞合所形成的格局，包括业务生态，公司生态和产业生态三个层次，而不同层次的每个生态都由生态主和其影响范围内的资源携带者构成。理解不同的生态层次是进行生态分析的基础。"
        }
      ],
      createList: [
        {
          title: "西井科技 WestWellLab",
          info: "类脑强人工智能商业公司",
          avatar: require("../../static/images/create1.png")
        },
        {
          title: "图森未来 TuSimple",
          info: "城际物流运输自动驾驶解决方案提供商",
          avatar: require("../../static/images/create2.jpg")
        },
        {
          title: "云从科技",
          info: "人脸识别及计算机视觉",
          avatar: require("../../static/images/create3.jpg")
        }
      ],
      applyList: [
        "创业公司立即报名提交信息的好处：",
        "1.优质的展示和访谈机会",
        "2.获得投资人的关注",
        "3.虎嗅提供的创业支持服务"
      ],
      hotList: [
        {
          img: require("../../static/images/hot1.jpg"),
          title: "谁浇了李彦宏一瓶冷水？"
        },
        {
          img: require("../../static/images/hot2.jpg"),
          title: "特斯拉：四个二带俩王"
        },
        {
          img: require("../../static/images/hot3.jpg"),
          title: "日本膨胀，韩国晕菜，十六国背着美国开小会"
        },
        {
          img: require("../../static/images/hot4.jpg"),
          title: "中国选手没有价值吗？"
        }
      ]
    };
  },
  methods: {

    toA() {
      this.$router.push('/a')
    }
  },
  mounted() {
    AOS.init({
			// easing: 'ease-out-back',
			duration: 1000
    });
    console.log(this.$router)
  },
};
</script>

<style lang="less">
@import "../../static/less/main.less";
</style>
