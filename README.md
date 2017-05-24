<h3>日常开发总结</h3>

<ul>
<li><a href="#Compatibility">兼容性问题</a></li>
</ul>


<h4 id="Compatibility"> 兼容性问题 </h4>
<strong>支付宝环境</strong>  android 测试机  moto x（第二代）  android版本5.1  ios9-3-2

1. 安卓版本采用的浏览器内核为老版uc   ios版为apple webkit 按常识应该是跟随手机系统走 兼容性良好

2. 安卓版中不支持flex布局  测试过display: box、display: flexbox、display: flex、 display:-webkit-flex 都无效 

3. 安卓版中css3效果应加前缀-webkit-，测试证明 老版uc支持-webkit-前缀 （手机内核现在基本都是webkit 所以可以不考虑-mos- -o-等）  如垂直居中问题 
    position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%); 
    transform: translate(-50%, -50%);

4. ios版动态事件绑定问题 待测 待解决  有时直接绑定到body上会不生效
    **  补充问题描述  click不生效  touchstart生效  
