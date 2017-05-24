<h3>日常开发总结</h3>

<ul>
<li><a href="node">node 相关</a></li>
<li><a href="#Compatibility">兼容性问题</a></li>
</ul>
<h4 id="node"> node 相关 </h4>
windows环境 : 

1. nodejs 中奇数版本为不稳定版本

2. node与npm的版本号并不相同  npm版本可以通过执行命令
<code>npm update -g npm</code>
如果没有更新下载东西 则表明是最新版本

3. 安装gulp grunt 等管理工具  需要在项目目录下执行下本身的安装命令   在电脑全局运行不会生效

4. 安装node-sass时，遇到的错误MSBUILD: error MSB3428 Visual C++ VCBuild.exe 1) .NET Framework 2.0 SDK Microsoft 
需安装淘宝镜像 <em>（建议安装node的时候就安上）</em>，然后使用cnpm安装node-sass

<code>
$ npm install cnpm -g --registry=https://registry.npm.taobao.org<br/>
$ cnpm install node-sass --registry=https://registry.npm.taobao.org
</code>

5. <a href="nvm">nvm</a> 可以控制使用的nodejs版本



<h4 id="Compatibility"> 兼容性问题 </h4>
<em>支付宝环境 （android 测试机  moto x（第二代）  android版本5.1  ios9-3-2）</em>  

1. 安卓版本采用的浏览器内核为老版uc   ios版为apple webkit 按常识应该是跟随手机系统走 兼容性良好

2. 安卓版中不支持flex布局  测试过display: box、display: flexbox、display: flex、 display:-webkit-flex 都无效 

3. 安卓版中css3效果应加前缀-webkit-，测试证明 老版uc支持-webkit-前缀 （手机内核现在基本都是webkit 所以可以不考虑-mos- -o-等）  如垂直居中问题 
  
  <code>
   position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%); 
    transform: translate(-50%, -50%);
</code>

4. ios版动态事件绑定问题 待测 待解决  有时直接绑定到body上会不生效
    **  补充问题描述  click不生效  touchstart生效  
