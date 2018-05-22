<template>
  <div id="app">
<transition enter-active-class="animated lightSpeedIn" leave-active-class="animated lightSpeedOut">
 <pre class="word" v-show="index === 0">
       {{code}}
 </pre>
</transition>
<transition enter-active-class="animated rotateIn" leave-active-class="animated rotateOut">
  <div class="myheart" v-show="index === 1"> 
       <span >
<i class="iconfont icon-heart" @click="clickHeart"></i>
       </span>
       <pre>↑
收取我的小心心呀
       </pre>
  </div>
</transition>
<transition enter-active-class="animated lightSpeedIn" leave-active-class="animated lightSpeedOut">
  <div class="final" v-show="index === 2">
      <pre>
         {{code2}}
      </pre>
      
  </div>
</transition >
    
   
    
    
  </div>
</template>

<script>


export default {
  name: 'App',
  methods:{
  clickHeart(){
    this.index = -1
      setTimeout(()=>{
          this.index = 2
          this.timer2 = setInterval(()=>{
                 if(this.N <= this.final2.length ){
        this.N += 1;
        this.code2 = this.final2.slice(0,this.N)
      }else{
        clearInterval(this.timer)
        
       
      }
          },100)
        },300)
      
  }
  },
  data(){
    return {
      code:``,
      code2:``,
final1:`自从我们认得啊，我算算.......
差不多3000多天快九年啦。
你看认得这么久，有很多事情都变了
但是有些事情一点都没变ε=(´ο｀*)))哎
很久之前你也会不高兴，我从来都不知道原因
不知道是我笨，还是的确没有人知道
你有没很期待有个人能很明白你心情呢
`,
      n:0,
      timer: null,
      timer2:null,
      index:-1,
      final2:`收了我的心要对我负责啊嘻嘻
这几天想着要走了哎，一开始还很开心的，
后来发现自己一点都不想去了
去了以后感觉下班以后都一个人哎
你可能都忙也不会有时间陪我
其实好烦啊
如果没有和你在一起
我觉得我去北京不会有感觉
希望以后不是你通知我你结婚了
而是我们真的到最后咯
还有好多话要说，
我想留到以后去说了
`,
      audio:null,
      N:0
    }
  },
  created(){
    this.audio = new Audio();
    this.audio.autoplay = true;
    this.audio.volume = 0.5
    this.audio.src = "http://dl.stream.qqmusic.qq.com/C400003bdk0E4ffToY.m4a?vkey=EDADC4EEC871E9474FF354B8546720719ABEB7D46D5945E3147A9674E14A251F04B8969BFD08AF2EF9A63CE0E53CC74E4A76D055AFEA0319&guid=7822771012&uin=1162374744&fromtag=663";
    
    setTimeout(()=>{
      this.index += 1
    },500)
    this.timer = setInterval(()=>{
      if(this.n <= this.final1.length ){
        this.n += 1;
        this.code = this.final1.slice(0,this.n)
      }else{
        clearInterval(this.timer)
        this.index = -1
        setTimeout(()=>{
          this.index = 1
        },800)
      }
    },100)
    
  }
}
</script>

<style >
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top:20px
}
.myheart{
  text-align: center
}
.iconfont{
  font-size: 6em;
  color: red;
}

</style>
