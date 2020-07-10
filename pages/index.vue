<template>
  <section class="container">
    <div>
      <h1 class="title">lottie-vue-sample</h1>
      <!--  先程作ったlottieコンポーネントを呼び出し、 そのときにjsonのデータを受け渡す。  -->
      <lottie class="asset" :options="defaultOptions" :height="600" :width="600" v-on:animCreated="handleAnimation"/>
    </div>
  </section>
</template>

<script>
import Lottie from "~/components/Lottie.vue";

// JSONデータを読み込み
import * as animationData from "~/assets/asset.json";

export default {
  components: {
    Lottie
  },
  data() {
    return {
      // データを定義
      defaultOptions: { animationData: animationData },
      animationSpeed: 1
    };
  },
  methods: {
    handleAnimation: function(anim) {
      this.anim = anim;
    },


  }
};
</script>

<style>
body{
  background-color: gainsboro;
  text-align: center;
}

h1 {
  margin: 80px;
}

</style>
