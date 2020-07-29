<template>
  <footer class="footer">
    <div class="container">
      <section>
        <a href v-for="(item, index) in alink" :key="index" class="link">{{ item.name }}</a>
      </section>
      <section class="clearfix">
        <p class="fl">
          Copyright ©
          <a href>网</a>
          <!-- <a href>京ICP备12013432号-1</a> -->
          <img src="../../../static/images/wj.png" alt />
          <!-- <a href>京公网安备 11010102001402号</a> -->
          &nbsp;&nbsp;&nbsp;
          本站由
          <img
            src="../../../static/images/aliyun.png"
            alt
            class="aliyun"
          />
          提供计算与安全服务
        </p>
        <section class="fr">
          <ul class="clearfix">
            <li>
              <span></span>
              <div>
                <img src="../../../static/images/huxiu_com.png" alt />
              </div>
            </li>
            <li>
              <span></span>
              <div>
                <img src="../../../static/images/apple_code.png" alt />
              </div>
            </li>
            <li>
              <span></span>
              <div>
                <img src="../../../static/images/android_code.png" alt />
              </div>
            </li>
          </ul>
        </section>
      </section>
    </div>
    <section class="floatbox">
    <section class="msg">
        <span>用户反馈</span>
        <div>
        <i></i>
        </div>
    </section>
    <section class="code">
        <p>
        <img src="../../../static/images/return_code.png" alt />
        <em>虎嗅APP</em>
        </p>
        <div>
        <i></i>
        </div>
    </section>
    <section class="return" @click="returnTop">
        <span>回到顶部</span>
        <div>
        <i></i>
        </div>
    </section>
    </section>
  </footer>
</template>

<script>
import $ from "jquery";
export default {
  data() {
    return {
      alink: [
        {
          name: "关于我们"
        },
        {
          name: "加入我们"
        },
        {
          name: "合作伙伴"
        },
        {
          name: "防网络诈骗专题"
        }
      ]
    };
  },
  methods: {
    returnTop() {
      this.$nextTick(() => {
        $("html,body").animate({ scrollTop: 0 }, "fase");
      });
    }
  },
  mounted() {
    var scrollTop = $(".footer").offset().top;
    this.$nextTick(() => {
      $(window).scroll(() => {
        var distance = $(window).scrollTop();
        if (distance > 500) {
          $(".return").fadeIn(500);
        } else {
          $(".return").fadeOut(500);
        }
        var height = $(window).height();
        if (distance + height >= scrollTop) { 
          $('.floatbox').css({
            bottom: '160px'
          })
        } else {
          $('.floatbox').css({
            bottom: '30px'
          })
        }
      });
    });
  }
};
</script>

<style lang="less">
@import "../../../static/less/footer.less";
</style>
