<template><div><h1 id="哈希值" tabindex="-1"><a class="header-anchor" href="#哈希值" aria-hidden="true">#</a> 哈希值</h1>
<hr>
<p>哈希是将目标文本转换成具有相同长度的、不可逆的杂凑字符串(或叫消息摘要)。</p>
<h2 id="常见的哈希算法" tabindex="-1"><a class="header-anchor" href="#常见的哈希算法" aria-hidden="true">#</a> 常见的哈希算法</h2>
<ul>
<li>
<p>CRC</p>
</li>
<li>
<p>MD4</p>
</li>
<li>
<p>MD5(128 bit)</p>
</li>
<li>
<p>SHA-1(160 bit)</p>
</li>
<li>
<p>SHA-2(256 bit)</p>
<p>目标文本 → Hash函数 → 消息摘要值</p>
</li>
</ul>
<blockquote>
<p>不同哈希算法进行哈希计算最终生成的哈希值长度不同</p>
</blockquote>
<table>
<thead>
<tr>
<th style="text-align:left">哈希算法</th>
<th style="text-align:left">长度</th>
<th style="text-align:left">摘要值字符数</th>
<th style="text-align:left">哈希值摘要值范例</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">MD5</td>
<td style="text-align:left">128bit</td>
<td style="text-align:left">32个</td>
<td style="text-align:left">e10adc3949ba59abbe56e057f20f883e</td>
</tr>
<tr>
<td style="text-align:left">SHA-1</td>
<td style="text-align:left">160bit</td>
<td style="text-align:left">40个</td>
<td style="text-align:left">7c4a8d09ca3762af61e59520943dc26494f8941b</td>
</tr>
<tr>
<td style="text-align:left">SHA-2</td>
<td style="text-align:left">256bit</td>
<td style="text-align:left">64个</td>
<td style="text-align:left">8d969eef6ecad3c29a3a629280e686cf0c3f5d5a86aff3ca12020c923adc6c92</td>
</tr>
<tr>
<td style="text-align:left">SHA-3</td>
<td style="text-align:left">512bit</td>
<td style="text-align:left">128个</td>
<td style="text-align:left">ba3253876aed6bc22d4a6ff53d8406c6ad864195ed144ab5c87621b6c233b548baeae6956df346ec8c17f5ea10f35ee3cbc514797ed7ddd3145464e2a0bab413</td>
</tr>
</tbody>
</table>
<h2 id="哈希碰撞" tabindex="-1"><a class="header-anchor" href="#哈希碰撞" aria-hidden="true">#</a> 哈希碰撞</h2>
<p>是指不同的信息通过某种哈希算法进行计算生成的摘要值相同,就称之为碰撞。目前已经发现MD5、SHA-1等哈希算法均存在一定概率的哈希碰撞。</p>
<p><a href="http://www.win.tue.nl/hashclash/SoftIntCodeSign/HelloWorld-colliding.exe" target="_blank" rel="noopener noreferrer">http://www.win.tue.nl/hashclash/SoftIntCodeSign/HelloWorld-colliding.exe<ExternalLinkIcon/></a></p>
<p><a href="http://www.win.tue.nl/hashclash/SoftIntCodeSign/GoodbyeWorld-colliding.exe" target="_blank" rel="noopener noreferrer">http://www.win.tue.nl/hashclash/SoftIntCodeSign/GoodbyeWorld-colliding.exe<ExternalLinkIcon/></a></p>
<p>这两个程序会在屏幕上打印出不同的字符，但是它们的 MD5 都是一样的。</p>
<h3 id="快速-md5-碰撞生成器" tabindex="-1"><a class="header-anchor" href="#快速-md5-碰撞生成器" aria-hidden="true">#</a> 快速 MD5 碰撞生成器</h3>
<p><a href="http://www.win.tue.nl/hashclash/fastcoll_v1.0.0.5.exe.zip" target="_blank" rel="noopener noreferrer">http://www.win.tue.nl/hashclash/fastcoll_v1.0.0.5.exe.zip<ExternalLinkIcon/></a></p>
<p>源代码：<a href="http://www.win.tue.nl/hashclash/fastcoll_v1.0.0.5_source.zip" target="_blank" rel="noopener noreferrer">http://www.win.tue.nl/hashclash/fastcoll_v1.0.0.5_source.zip<ExternalLinkIcon/></a></p>
<h2 id="哈希应用" tabindex="-1"><a class="header-anchor" href="#哈希应用" aria-hidden="true">#</a> 哈希应用</h2>
<p>常用于数据的一次性校验</p>
<h3 id="应用场景" tabindex="-1"><a class="header-anchor" href="#应用场景" aria-hidden="true">#</a> 应用场景</h3>
<ol>
<li>常用于证据保全，验证数据一致性(磁盘或文件内容被修改，可快速发现问题)</li>
<li>文件内容比较，快速找到相同文件，实现特定文件快速发现或排除。</li>
<li>密码保护<br>
范例：原文密码：123456<br>
第一轮md5：e10adc3949ba59abbe56e057f20f883e<br>
第二轮md5：14e1b600b1fd579f47433b88e8d85291</li>
</ol>
<h2 id="哈希计算工具" tabindex="-1"><a class="header-anchor" href="#哈希计算工具" aria-hidden="true">#</a> 哈希计算工具</h2>
<h3 id="windows自带" tabindex="-1"><a class="header-anchor" href="#windows自带" aria-hidden="true">#</a> Windows自带</h3>
<div class="language-powershell line-numbers-mode" data-ext="powershell"><pre v-pre class="language-powershell"><code><span class="token function">Get-FileHash</span> 文件名 <span class="token operator">-</span>Algorithm MD5
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><p>Copy</p>
<blockquote>
<p>请在Powershell中使用此命令</p>
</blockquote>
<p>此处MD5可替代为<code v-pre>SHA1</code> <code v-pre>SHA256</code> <code v-pre>SHA384</code> <code v-pre>SHA512</code>等等</p>
<h3 id="第三方工具" tabindex="-1"><a class="header-anchor" href="#第三方工具" aria-hidden="true">#</a> 第三方工具</h3>
<h4 id="hashmyfiles" tabindex="-1"><a class="header-anchor" href="#hashmyfiles" aria-hidden="true">#</a> HashMyFiles</h4>
<figure><img src="https://bu.dusays.com/2022/11/21/637a54e942152.png" alt="image-20221121002519292" tabindex="0" loading="lazy"><figcaption>image-20221121002519292</figcaption></figure>
<blockquote>
<p>下载地址：<a href="https://hashmyfiles.en.softonic.com/" target="_blank" rel="noopener noreferrer">https://hashmyfiles.en.softonic.com/<ExternalLinkIcon/></a></p>
</blockquote>
<h4 id="hashcalculator" tabindex="-1"><a class="header-anchor" href="#hashcalculator" aria-hidden="true">#</a> HashCalculator</h4>
<figure><img src="https://bu.dusays.com/2022/11/21/637a550bd8732.png" alt="image-20221121002553900" tabindex="0" loading="lazy"><figcaption>image-20221121002553900</figcaption></figure>
<blockquote>
<p>下载地址：<a href="https://sourceforge.net/projects/hashcalculator/" target="_blank" rel="noopener noreferrer">https://sourceforge.net/projects/hashcalculator/<ExternalLinkIcon/></a></p>
</blockquote>
</div></template>


