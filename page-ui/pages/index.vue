<template>
  <div class="m">
    <div class="r bn swiper-container" v-if="resData.banners && resData.banners[0]">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="bann in resData.banners">
          <div class="b">
            <div class="bg bgb"><img :src="bann.sourceShow" /></div>
            <div class="bi bib">
              <h1 class="bz">{{ bann.title }}</h1>
              <p class="bz">{{ bann.summary }}</p>
              <div class="bia"><NuxtLink class="bz" :to="bann.url">点击前往</NuxtLink></div>
            </div>
          </div>
        </div>
      </div>
      <!-- Add Pagination -->
      <div class="swiper-pagination"></div>
    </div>
    <div class="r">
      <div class="rb rt">
        <NuxtLink class="b b4" v-for="other in postsMain" :to="'/posts/' + other.url">
          <div class="bg"><i class="bz" v-html="other.icon"></i></div>
          <div class="bi">
            <h2 class="bz">{{ other.tip }}</h2>
            <div class="bit">
              <span class="bz">{{ other.desc }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <!--广告位 -->
    <div class="addeare"><Adsbygoogle ad-slot="9517100589" /></div>

    <div class="r">
      <div class="rp">
        <h1 class="bz"><i>&#xF007;</i> 近期上升</h1>
      </div>
      <div class="rb" v-if="resData.postsHot && resData.postsHot[0]">
        <NuxtLink class="b b3" v-for="post in resData.postsHot" :to="'/post/' + post.url">
          <div class="bg">
            <img :src="post.sourcePath + '_1.' + post.sourceBack" />
            <div class="bgt">
              <span class="bz"><i>&#xF013;</i>{{ post.categoryName }}</span>
              <span class="bz"><i>&#xF007;</i>{{ post.hots }}</span>
            </div>
          </div>
          <div class="bi">
            <h1 class="bz">📖{{ post.title }}</h1>
            <div class="bit">
              <span class="bz" v-for="t in post.tagNames"><i>#</i>{{ t }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <div class="r">
      <div class="rp">
        <h1><i>&#xF012;</i> 文章分类</h1>
      </div>
      <div class="rb rt rtg" v-if="resData.category && resData.category[0]">
        <NuxtLink v-for="cat in resData.category" :to="'/category/' + cat.url" class="b b4">
          <div class="bg"><img :src="cat.sourceShow" /></div>
          <div class="bi">
            <span class="bno bz">{{ cat.num }}</span>
            <h2 class="bz">{{ cat.title }}</h2>
            <div class="bit">
              <span class="bz">{{ cat.summary }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <div class="r">
      <div class="rp">
        <h1><i>&#xF010;</i> 全站热门</h1>
      </div>
      <div class="rb" v-if="resData.postsView && resData.postsView[0]">
        <NuxtLink class="b b3" v-for="post in resData.postsView" :to="'/post/' + post.url">
          <div class="bg">
            <img :src="post.sourcePath + '_1.' + post.sourceBack" />
            <div class="bgt">
              <span class="bz"><i>&#xF013;</i>{{ post.categoryName }}</span>
              <span class="bz"><i>&#xF010;</i>{{ post.views }}</span>
            </div>
          </div>
          <div class="bi">
            <h1 class="bz">📖{{ post.title }}</h1>
            <div class="bit">
              <span class="bz" v-for="t in post.tagNames"><i>#</i>{{ t }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <div class="r">
      <div class="rp">
        <h1><i>&#xF013;</i> 核心标签</h1>
      </div>
      <div class="rb rt rtt" v-if="resData.tag && resData.tag[0]">
        <NuxtLink v-for="ta in resData.tag" :to="'/tag/' + ta.url" class="b b5">
          <div class="bg"><img :src="ta.sourceShow" /></div>
          <div class="bi">
            <h2 class="bz">{{ ta.title }}</h2>
          </div>
        </NuxtLink>
      </div>
    </div>
    <div class="r">
      <div class="rp">
        <h1><i>&#xF011;</i> 深度好文</h1>
      </div>
      <div class="rb" v-if="resData.postsGood && resData.postsGood[0]">
        <NuxtLink class="b b3" v-for="post in resData.postsGood" :to="'/post/' + post.url">
          <div class="bg">
            <img :src="post.sourcePath + '_1.' + post.sourceBack" />
            <div class="bgt">
              <span class="bz"><i>&#xF013;</i>{{ post.categoryName }}</span>
              <span class="bz"><i>&#xF011;</i>{{ post.goods }}</span>
            </div>
          </div>
          <div class="bi">
            <h1 class="bz">📖{{ post.title }}</h1>
            <div class="bit">
              <span class="bz" v-for="t in post.tagNames"><i>#</i>{{ t }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <!--广告位 -->
    <div class="addeare"><Adsbygoogle ad-slot="6275342659" /></div>
    <div class="r">
      <div class="rp">
        <h1><i>&#xF008;</i> 新鲜发布</h1>
      </div>
      <div class="rb" v-if="resData.postsNew && resData.postsNew[0]">
        <NuxtLink class="b b3" v-for="post in resData.postsNew" :to="'/post/' + post.url">
          <div class="bg">
            <img :src="post.sourcePath + '_1.' + post.sourceBack" />
            <div class="bgt">
              <span class="bz"><i>&#xF013;</i>{{ post.categoryName }}</span>
              <span class="bz"><i>&#xF008;</i>{{ post.pushAt }}</span>
            </div>
          </div>
          <div class="bi">
            <h1 class="bz">📖{{ post.title }}</h1>
            <div class="bit">
              <span class="bz" v-for="t in post.tagNames"><i>#</i>{{ t }}</span>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
    <div class="r">
      <NuxtLink class="b bm" to="/posts/new">查看更多<em></em></NuxtLink>
    </div>
    <Foot></Foot>
  </div>
</template>
<script setup lang="ts">
import "swiper/css/bundle";
import { Swiper } from "swiper";
import { Pagination } from "swiper/modules";
import { InitDom, InitBack, LoadBannImg } from "~/utils/base.js";
const runtimeConfig = useRuntimeConfig();
const needRun = useState("indexRun", () => true);
const resData = useState("resData", () => <any>{});
useHead({
  title: `臻林(Wen-Jay)'s blog Welcome!${runtimeConfig.public.siteName}`,
  meta: [{ hid: "description", name: "description", content: `${runtimeConfig.public.description}` }],
  //link: [{ href: "https://cdn.staticfile.net/Swiper/11.0.5/swiper-bundle.min.css", rel: "stylesheet" }],
  //script: [{ src: "https://cdn.staticfile.net/Swiper/11.0.5/swiper-bundle.min.js", tagPosition: "bodyClose", onload: initSwiper }],
});
// 读取页面数据
if (process.server) {
  const res = await useFetch(runtimeConfig.public.backServer + "/page/index", {});
  resData.value = (res.data.value as any).data;
  needRun.value = false;
}
const postsMain = [
  { url: "hot", tip: "近期上升", desc: "最近备受关注的内容", icon: "&#xF007;" },
  { url: "view", tip: "全站热门", desc: "访问流量最高的内容", icon: "&#xF010;" },
  { url: "good", tip: "深度好文", desc: "深度价值指数的内容", icon: "&#xF011;" },
  { url: "new", tip: "新鲜发布", desc: "围观最新发布的内容", icon: "&#xF008;" },
];
// 页面挂载后的初始化
onMounted(async () => {
  // 如果SSR没有
  if (needRun.value) {
    await initByClient();
  }
  initPage();
});
async function initByClient() {
  const res = await $fetch("/api/page/index", { server: false, method: "GET" });
  resData.value = (res as any).data;
}
onUnmounted(() => {
  needRun.value = true;
  InitBack();
});
function initPage() {
  initSwiper();
  InitDom();
}
// Page Init (ext IE)
function initSwiper() {
  // banner
  new Swiper(".swiper-container", {
    modules: [Pagination],
    loop: true,
    autoplay: {
      disableOnInteraction: false,
      stopOnLastSlide: false,
      delay: 3500000,
    },
    grabCursor: true,
    speed: 400,
    pagination: { el: ".swiper-pagination", clickable: true },
    on: {
      init: function () {
        // @ts-ignore
        LoadBannImg();
      },
    },
  });
}
</script>
