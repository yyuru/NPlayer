<template>
  <div id="player">
    <Progress />
    <Browser  class="animated " :class="{'slideInLeft':!expand,'slideOutLeft':expand}"></Browser>
    <List  class="animated " :class="{'slideInRight':!expand,'slideOutRight':expand}"></List>
    <Btnlist class="animated fadeIn"></Btnlist>
    <Words class="animated" :class="{'fadeIn':expand,'fadeOut':!expand}"></Words>
    <Visual v-if="playing" />
  </div>
</template>
<script>
import Btnlist from "./components/btnlist/btnlist"
import Progress from "./components/progress/progress"
import Browser from "./songbrowser/browser"
import List from "./songlist/list"
import Words from './words/words'
import Visual from './musicVisual/visual'
import {mapGetters,mapActions,mapMutations} from 'vuex'
export default {
  data(){
    return {
      //played:document.getElementsByTagName("audio")[0].ended
    }
  },
  components:{
    Btnlist,
    List,
    Browser,
    Words,
    Progress,
    Visual
  },
  computed:{
    
    ...mapGetters([
      'audio',
      'expand',
      'currentIndex',
      'currentMusic',
      'playing'
    ])
  },
  watch:{
    
  }
}
</script>
<style lang="stylus" scoped>
  #player{
    position absolute 
    top 0
    bottom 0
    left 0
    right 0
    //background-size 100% 100%
    background-position: center
    background url('../../static/images/bg.jpg')
    .animated{
      animation-duration: 2.5s;    //动画持续时间
      
    }
  }
  
</style>
