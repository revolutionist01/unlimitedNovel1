 <template>
  <div class="footer">
    <div class="box_center cf">
      <div class="copyright">
        <ul>
          <li class="menu">
            <a href="/?to=mobile">手机站</a><i class="line">|</i
            ><a href="/">网站首页</a><i class="line">|</i
            ><a href="/about/default.html">关于我们</a><i class="line">|</i
            ><a href="/about/contact.html">联系我们</a><i class="line">|</i
            ><a href="javascript:void(0)" @click="goFeedBack">反馈留言</a><i class="line">|</i><a href="/author/index.html">作家专区</a
            ><i class="line">|</i><a href="/mobile/fiction_house.apk">客户端</a>
          </li>
          <li>
            Copyright (C) https://github.com/revolutionist01/unlimitedNovel1 All rights
            reserved&nbsp;&nbsp;无限阅读小组版权所有
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import { useRouter } from "vue-router";
import { getToken } from "@/utils/auth";
export default {
  name: "Footer",
  setup() {
    const router = useRouter();
    const goFeedBack = () => {
      if(!getToken()){
        router.push({name: 'login'});
      }else{
      router.push({name: 'feadback'});
      }
    };
    return {
      goFeedBack
    }
  },

};
</script>
