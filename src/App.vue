<template>
  <div id="app">
    <div v-html="styleCode"></div>
    <div class="code-ct" ref="container"><pre  v-html="highlightedCode">{{code}}</pre></div>
    <div class="resume-ct" v-html="resumeHtml" ref="resumecontainer"></div>
    <div v-html="resumestyle"></div>
  </div>
</template>
<script>
  import Prism from 'prismjs'
  export default {
    name: 'app',
    data () {
      return {
        time1: '',
        time2: '',
        time3: '',
        code: '',
        styleCode: '',
        resumeHtml: '',
        resumestyle: '',
        styleSentence: [`
 /**
  * 您好！
  * 您能看到这个网页是我的荣幸。
  * 这真是一件令人开心的事，因为...  
  *          
  * 这是我的个人简历  (￣︶￣)↗
  */

 /** 
  * 我要开始咯~ 
  * 先来点过渡效果吧 
  */

* {
  margin: 0;
  padding: 0;
  -webkit-transition: all .3s;
          transition: all .3s;
}

/* 屏幕太亮容易伤眼睛哦。。。 */
html {
  background: rgb(63, 82, 99);
}

/* 嗯，这颜色还不错。再加个边框吧！ */
.code-ct {
  float: left;
  padding: 20px;
  margin: 10px;
  border: 1px solid #eee;
  overflow: auto;
  background: rgb(48, 48, 48);  
  width: 40vw;
  height: 90vh; 
  color: #ccc;    
  box-shadow: 5px 5px 10px rgba(255,255,255,.3);
}

/* 要是有点高亮效果就好了 */
.token.comment{ color: #857f6b; font-style: italic;}
.token.selector{ color: #db4437; }
.token.property{ color: #4285f4; }
.token.punctuation{ color: #f4b400; }
.token.function{ color: #0f9d58; }

/* 要不，再来点3D效果？ */
html {
  -webkit-perspective: 1000px;
          perspective: 1000px;
}
.code-ct,pre {
  -webkit-transition: 1s;
          transition: 1s;
  -webkit-transform: rotateY(10deg) translateZ(-50px);
          transform: rotateY(10deg) translateZ(-50px);

}

/* 好了，我现在要找一个看着顺眼的位置。。。 */
.resume-ct {
  position: absolute;
  right: 0;
  width: 45vw;
  height: 90vh;
  overflow: auto;
  margin-right: 40px;
  margin-top: 29px;
  -webkit-transition: 1s;
          transition: 1s;
}
.code-ct {
  margin-left: 55vw;
  -webkit-transform: rotateY(-10deg) translateZ(-50px);
          transform: rotateY(-10deg) translateZ(-50px);
  box-shadow: -5px 5px 10px rgba(255,255,255,.3);
}
.resume-ct {
  background-color: #eee;
  right: 47vw;
}                                                           
   
/* 现在，请允许我介绍一下我自己 */
     `, `
    <h2 class="name">王康</h2>
    <p class="base-info">男，25岁，毕业于江苏师范大学</p>
    <p>电话：13675209645   邮箱：wangkang3034@163.com</p>
    <h3 class="title">工作经历</h3>
    <p>2015 年 1 月至 2016 年 5 月就职于 连云港铭华环保材料有限公司</p>
    <p>任前端开发工程师</p>
    <p>全面负责公司官网的开发与维护。主要使用HTML、CSS、JavaScript（jQuery）等前端主流技术。并使用了“双飞翼”布局，响应式开发等方法。</p>
    <h3 class="title">项目经验/作品展示</h3>
    <ul class="works">
<!-- 音乐播放器 -->
      <li>
        <ul>
          <li class="work-name">FM_music: 一个美观好用的 FM 音乐播放器</li>
          <li class="method">
            <span><b>使用技术：</b></span>
            <p>HTML5 / CSS3动画 / jQuery / 函数封装 / ajax </p>
          </li>
          <li class="sketch">
            <span><b>功能描述：</b></span>
            <ul>
              <li><span>a.</span><p>该项目为本人独立开发，原创的UI设计。使用CSS3动画，HTML5-media技术，同时实现了JS代码封装；</p></li>
              <li><span>b.</span><p>使用ajax获取音乐资源；并对获取的json文件进行相应的操作，实现歌词显示、音频播放；</p></li>
              <li><span>c.</span><p>具有丰富的动画效果，人性化的操作逻辑，使用方便；</p></li>
            </ul>
          </li>
          <li class="address"><a href="http://wkfmmusic.applinzi.com/" target="_bank">项目预览</a></li>
        </ul>
      </li>
<!-- TODO_List -->
      <li>
        <ul>
          <li class="work-name">
          TODO_List: 待办事项管理工具
          </li>
          <li class="method">
            <span><b>使用技术：</b></span>
            <p>Vue.js / Web Storage </p>
          </li>
          <li class="sketch">
            <span><b>功能描述：</b></span>
            <ul>
              <li><span>a.</span><p>本工具用于记录和查询待办事项，且方便进行标记、修改和删除等操作；</p></li>
              <li><span>b.</span><p>通过操作LocalStorage实现内容本地存储；</p></li>
            </ul>
          </li>
          <li class="address"><a href="https://godlovekang.github.io/todolistByVue/index.html" target="_bank">项目预览</a></li>
        </ul>
      </li>
<!-- translation-tool -->
      <li>
         <ul>
          <li class="work-name">
          translation-tool: 一个便捷实用的翻译工具
          </li>
          <li class="method">
            <span><b>使用技术：</b></span>
            <p>Node.js / jQuery / ajax / npm 包管理器</p>
          </li>
          <li class="sketch">
            <span><b>功能描述：</b></span>
            <ul>
              <li><span>a.</span><p>该项目由本人独立开发并发布至npm包管理系统</p></li>
              <li><span>b.</span><p>这是一个使用 Node.js 编写的命令行工具，使用 ajax 通过有道翻译API实现英汉互译；</p></li>
              <li><span>c.</span><p>使用 jQuery 对API返回的json格式数据进行处理，使其输出样式美观、条理清晰；可通过命令行安装使用。</p></li>
            </ul>
          </li>
          <li class="address"><a href="https://www.npmjs.com/package/translation-tool" target="_bank">npm 地址</a></li>
        </ul>
      </li>
<!-- 官网首页 -->
      <li>
        <ul>
          <li class="work-name">
          某公司官方商城首页
          </li>
          <li class="method">
            <span><b>使用技术：</b></span>
            <p>RequireJS / jQuery / CSS3 / HTML / 面向对象封装</p>
          </li>
          <li class="sketch">
            <span><b>功能描述：</b></span>
            <ul>
              <li><span>a.</span><p>使用了 RequireJS 框架，并对 JS 代码进行封装，实现了模块化编程；</p></li>
              <li><span>b.</span><p>使用 CSS3, JS 实现轮播窗口随的3D-hover效果；使用了大量的CSS、jQuery动画；</p></li>
            </ul>
          </li>
          <li class="address"><a href="https://godlovekang.github.io/smartisan/smartisan.html" target="_bank">项目预览</a></li>
        </ul>
      </li>
<!-- datepicker  -->
      <li>
            <ul>
          <li class="work-name">
          Datepicker: 一个直观易用的日期选择插件
          </li>
          <li class="method">
            <span><b>使用技术：</b></span>
            <p> jQuery插件 / 代码封装</p>
          </li>
          <li class="sketch">
            <span><b>功能描述：</b></span>
            <ul>
              <li><span>a.</span><p>本插件能为需要输入日期的 input文本框 提供日期选择模块；</p></li>
              <li><span>b.</span><p>本插件引用非常方便，设计简洁美观。</p></li>
            </ul>
          </li>
          <li class="address"><a href="https://godlovekang.github.io/Datepidker/datepicker.html" target="_bank">项目预览</a></li>
        </ul>
      </li>
      <h3 class="title">技能汇总</h3>
      <ul class="skills">
        <li><span class="seq">1.</span> <p></p>精通主流的前端开发技术，HTML、CSS、JavaScript、Ajax、JSON等，熟练使用Jquery；</li>
        <li><span class="seq">2.</span><p></p>熟练使用 Less 等预编译语言，熟悉HTML5、CSS3等，能用其完成丰富的页面效果；</li>
        <li><span class="seq">3.</span><p></p>熟悉各种浏览器的开发调试方法。熟练使用 Git，Submit，Linux 命令行等开发工具；</li>
        <li><span class="seq">4.</span><p></p>能够基于面向对象思想对 JS 代码进行模块化封装；</li>
        <li><span class="seq">5.</span><p></p>熟练使用 RequireJS，npm，Node.js 进行模块化编程。以及 Gulp等前端工程化工具；</li>
        <li><span class="seq">6.</span><p></p>熟悉搜索引擎优化（SEO）技术；熟悉 Web Storage、cookie、manifest 等本地存储技术；</li>
        <li><span class="seq">7.</span><p></p>能使用 Node.js 开发命令行工具；熟练使用 Bootstrap 、Vue.js等框架；</li>
        <li><span class="seq">8.</span><p></p>能熟练使用 Photoshop 的基本功能；</li>
        <li><span class="seq">9.</span><p></p>具有较高的审美能力，能够承担较强的工作压力。</li>
      </ul>
    </ul>
     `, `
/**                     
 * 额 ...
 * 这是什么鬼 ...            
 * 是不是感觉很乱？                            
 * 下面就是见证奇迹的时刻！          
 * 3 ...
 * 2 ...
 * 1 ...
 *   ......                 
 */    
     `, `
<style>
 * {
      margin: 0;
      padding: 0;
    }
    html {
      background: rgb(63, 82, 99);
    }
    a {
      text-decoration: none;
    }
    .resume-ct {
      position: absolute;
      right: 47vw;
      width: 45vw;
      height: 90vh;
      margin-right: 40px;
      margin-top: 29px;
      -webkit-transition: 1s;
      transition: 1s;
      background-color: #eee;
      color: rgba(0,0,0,.8);
      overflow: auto;
    }
    .resume-ct {
      box-sizing: border-box;
      padding: 10px;
      font-size: 14px;
    }
    ul li {
      list-style: none;
    }
    h2 {
      margin: 10px 0;
      font-size: 20px;
      font-weight: bold;
    }
    p {
      margin: 5px 0;
    }
    h3 {
      margin: 20px 0;
      font-size: 16px;
      font-weight: bold;
    }
    .works .work-name {
      color: #4285f4;
      margin: 10px 0;
    }
    .method span {
      float: left;
      display: inline-block;
      width: 80px;
      margin-bottom: 2px;
    }
    .method p {
      overflow: hidden;
    }
    .sketch>span {
      float: left;
      display: inline-block;
      width: 80px;
    }
    .sketch>ul {
      overflow: hidden;
    }
    .sketch>ul span {
      float: left;
      display: inline-block;
      width: 20px;
    }
    .sketch>ul p{
      overflow: hidden;
    }
    .address {
      margin-left: 80px;
      margin-top: 10px;
      margin-bottom: 30px;
    }
    .address a{
      display: inline-block;
      background-color: #4285f4;
      text-align: center;
      padding: 4px 10px;
      color: #fff;
    }
    .address a:hover {
      background-color: #527ed9;
    }
    .skills>li {
      margin: 5px 0;
    }
    .skills .seq {
      float: left;
      display: inline-block;
      width: 20px;
      padding-top: 4px;
    }
    .skills p {
      overflow: hidden;
    }
</style>
     `, `
/**
 * 好了，大功告成！      
 *       
 * 感谢您能耐心看完这份简历      
 * 真诚希望能够获得贵公司的面试机会      
 * 如您有意，可以拨打我的电话：13675209645      
 * 或者发送邮件至：wangkang3034@163.com      
 * 祝您工作顺利，生活愉快！      
 *
 * 王康       
 * 2017年3月                     
 */ 

 /**
  * 等你电话呦 (* /ω＼*)
  */  
     `
        ]
      }
    },
    computed: {
      highlightedCode: function () {
        return Prism.highlight(this.code, Prism.languages.css)
      }
    },
    watch: {
      code: function (val, oldval) {
        if (val.length === this.styleSentence[0].length) {
          clearInterval(this.time1)
          this.resumeHtml = this.styleSentence[1]
        }
        if (val.length === this.styleSentence[0].length + this.styleSentence[2].length) {
          clearInterval(this.time2)
          this.resumestyle = this.styleSentence[3]
        }
        this.$refs.container.scrollTop = 100000
      },
      resumeHtml: function (val, oldval) {
        if (val.length >= this.styleSentence[1].length) {
          this.$refs.resumecontainer.scrollTop = 0
          var k = 0
          this.time2 = setInterval(() => {
            this.code = this.styleSentence[0] + this.styleSentence[2].substring(0, k)
            k++
          }, 30)
        } else {
          this.$refs.resumecontainer.scrollTop = 100000
        }
      },
      resumestyle: function (val, oldval) {
        var i = 0
        this.time3 = setInterval(() => {
          this.code = this.styleSentence[0] + this.styleSentence[2] + this.styleSentence[4].substring(0, i)
          i++
        }, 100)
      }
    },
    created () {
      var n = 0
      console.log(this.styleSentence[0].length)
      this.time1 = setInterval(() => {
        this.code = this.styleSentence[0].substring(0, n)
        this.styleCode = '<style>' + this.code + '</style>'
        n++
      }, 50)
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

  }
  * {
    padding: 0;
    margin: 0;
  }
  pre {
    text-space: pre-line;
  }

</style>
