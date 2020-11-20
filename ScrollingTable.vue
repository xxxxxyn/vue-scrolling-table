<template>
    <div class="scroll-table">
      <ul id="scrolling-box"
          :style="{'animation-duration':(scrollContent.length*eachScrollTime)+'s','animation-play-state':'running'}"
      >
        <li v-for="( item ,index ) in scrollContent"
            :key="index">
          <span>{{item}}</span>
        </li>
        <li v-for="( item ,index ) in scrollContent"
            :key="index">
          <span>{{item}}</span>
        </li>
      </ul>
    </div>
</template>

<script>
  export default {
    name: "ScrollingTable",
    props: {
      eachScrollTime:{
        type: Number,
        default: 2,
        required: true,
      },
      scrollContent: {
        type: Array,
        default: ['line1', 'line2', 'line3', 'line4'],
        required: true,
      }
    },
    data() {
      return{
      }
    },
    computed: {
    }
  }
</script>

<style lang="less" scoped>

  .scroll-table {
    height: 150px;
    width: 100px;
    display: inline-block;
    overflow: hidden;
    position: relative;
    background-color: rgba(246, 187, 147, 0.9);
    color: #ff4000;
    font-size: 15px;

    ul#scrolling-box {
      animation: news-swiper 10s linear infinite;
      animation-play-state: paused;
      position: absolute;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: start;

      li {
        height: 30px;
        display: inline-block;
        span {
          display: inline-block;
        }
      }
    }
  }

  @keyframes news-swiper {
    0% {
      transform: translateY(0);
    }
    25% {
      transform: translateY(-12.5%);
    }
    50% {
      transform: translateY(-25%);
    }
    75% {
      transform: translateY(-37.5%);
    }
    99.99% {
      transform: translateY(-50.1%);
    }
    100% {
      transform: translateY(0);
    }

  }

</style>
