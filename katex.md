---


---

<h1 id="img-srchttpskhan.github.iokatexkatex-logo.svg-width130-altkatex"><a href="https://khan.github.io/KaTeX/"><img src="https://khan.github.io/KaTeX/katex-logo.svg" width="130" alt="KaTeX"></a></h1>
<p><a href="https://travis-ci.org/Khan/KaTeX"><img src="https://travis-ci.org/Khan/KaTeX.svg?branch=master" alt="Build Status"></a> <a href="https://codecov.io/gh/Khan/KaTeX"><img src="https://codecov.io/gh/Khan/KaTeX/branch/master/graph/badge.svg" alt="codecov"></a> <a href="https://gitter.im/Khan/KaTeX?utm_source=badge&amp;utm_medium=badge&amp;utm_campaign=pr-badge&amp;utm_content=badge"><img src="https://badges.gitter.im/Join%20Chat.svg" alt="Join the chat at https://gitter.im/Khan/KaTeX"></a></p>
<p><em>KaTeX</em> is a fast, easy-to-use JavaScript library for TeX math rendering on the web.</p>
<ul>
<li><strong>Fast:</strong> KaTeX renders its math synchronously and doesn’t need to reflow the page. See how it compares to a competitor in <a href="http://www.intmath.com/cg5/katex-mathjax-comparison.php">this speed test</a>.</li>
<li><strong>Print quality:</strong> KaTeX’s layout is based on Donald Knuth’s TeX, the gold standard for math typesetting.</li>
<li><strong>Self contained:</strong> KaTeX has no dependencies and can easily be bundled with your website resources.</li>
<li><strong>Server side rendering:</strong> KaTeX produces the same output regardless of browser or environment, so you can pre-render expressions using Node.js and send them as plain HTML.</li>
</ul>
<p>KaTeX supports all major browsers, including Chrome, Safari, Firefox, Opera, Edge, and IE 9 - IE 11. More information can be found on the <a href="https://khan.github.io/KaTeX/function-support.html">list of supported commands</a> and on the <a href="https://github.com/khan/katex/wiki">wiki</a>.</p>
<h2 id="usage">Usage</h2>
<p>You can <a href="https://github.com/khan/katex/releases">download KaTeX</a> and host it on your server or include the <code>katex.min.js</code> and <code>katex.min.css</code> files on your page directly from a CDN:</p>
<pre class=" language-html"><code class="prism  language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>link</span> <span class="token attr-name">rel</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>stylesheet<span class="token punctuation">"</span></span> <span class="token attr-name">href</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.9.0-beta1/katex.min.css<span class="token punctuation">"</span></span> <span class="token attr-name">integrity</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>sha384-VEnyslhHLHiYPca9KFkBB3CMeslnM9CzwjxsEbZTeA21JBm7tdLwKoZmCt3cZTYD<span class="token punctuation">"</span></span> <span class="token attr-name">crossorigin</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>anonymous<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span> <span class="token attr-name">src</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.9.0-beta1/katex.min.js<span class="token punctuation">"</span></span> <span class="token attr-name">integrity</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>sha384-O4hpKqcplNCe+jLuBVEXC10Rn1QEqAmX98lKAIFBEDxZI0a+6Z2w2n8AEtQbR4CD<span class="token punctuation">"</span></span> <span class="token attr-name">crossorigin</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>anonymous<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span><span class="token script language-javascript"></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>
</code></pre>
<h4 id="in-browser-rendering">In-browser rendering</h4>
<p>Call <code>katex.render</code> with a TeX expression and a DOM element to render into:</p>
<pre class=" language-js"><code class="prism  language-js">katex<span class="token punctuation">.</span><span class="token function">render</span><span class="token punctuation">(</span><span class="token string">"c = \\pm\\sqrt{a^2 + b^2}"</span><span class="token punctuation">,</span> element<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>If KaTeX can’t parse the expression, it throws a <code>katex.ParseError</code> error.</p>
<h4 id="server-side-rendering-or-rendering-to-a-string">Server side rendering or rendering to a string</h4>
<p>To generate HTML on the server or to generate an HTML string of the rendered math, you can use <code>katex.renderToString</code>:</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">var</span> html <span class="token operator">=</span> katex<span class="token punctuation">.</span><span class="token function">renderToString</span><span class="token punctuation">(</span><span class="token string">"c = \\pm\\sqrt{a^2 + b^2}"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token comment">// '&lt;span class="katex"&gt;...&lt;/span&gt;'</span>
</code></pre>
<p>Make sure to include the CSS and font files, but there is no need to include the JavaScript. Like <code>render</code>, <code>renderToString</code> throws if it can’t parse the expression.</p>
<h4 id="rendering-options">Rendering options</h4>
<p>You can provide an object of options as the last argument to <code>katex.render</code> and <code>katex.renderToString</code>. Available options are:</p>
<ul>
<li><code>displayMode</code>: <code>boolean</code>. If <code>true</code> the math will be rendered in display mode, which will put the math in display style (so <code>\int</code> and <code>\sum</code> are large, for example), and will center the math on the page on its own line. If <code>false</code> the math will be rendered in inline mode. (default: <code>false</code>)</li>
<li><code>throwOnError</code>: <code>boolean</code>. If <code>true</code>, KaTeX will throw a <code>ParseError</code> when it encounters an unsupported command. If <code>false</code>, KaTeX will render the unsupported command as text in the color given by <code>errorColor</code>. (default: <code>true</code>)</li>
<li><code>errorColor</code>: <code>string</code>. A color string given in the format <code>"#XXX"</code> or <code>"#XXXXXX"</code>. This option determines the color which unsupported commands are rendered in. (default: <code>#cc0000</code>)</li>
<li><code>macros</code>: <code>object</code>. A collection of custom macros. Each macro is a property with a name like <code>\name</code> (written <code>"\\name"</code> in JavaScript) which maps to a string that describes the expansion of the macro. Single-character keys can also be included in which case the character will be redefined as the given macro (similar to TeX active characters).</li>
<li><code>colorIsTextColor</code>: <code>boolean</code>. If <code>true</code>, <code>\color</code> will work like LaTeX’s <code>\textcolor</code>, and take two arguments (e.g., <code>\color{blue}{hello}</code>), which restores the old behavior of KaTeX (pre-0.8.0). If <code>false</code> (the default), <code>\color</code> will work like LaTeX’s <code>\color</code>, and take one argument (e.g., <code>\color{blue}hello</code>).  In both cases, <code>\textcolor</code> works as in LaTeX (e.g., <code>\textcolor{blue}{hello}</code>).</li>
<li><code>maxSize</code>: <code>number</code>. If non-zero, all user-specified sizes, e.g. in <code>\rule{500em}{500em}</code>, will be capped to <code>maxSize</code> ems. Otherwise, users can make elements and spaces arbitrarily large (the default behavior).</li>
</ul>
<p>For example:</p>
<pre class=" language-js"><code class="prism  language-js">katex<span class="token punctuation">.</span><span class="token function">render</span><span class="token punctuation">(</span><span class="token string">"c = \\pm\\sqrt{a^2 + b^2}\\in\\RR"</span><span class="token punctuation">,</span> element<span class="token punctuation">,</span> <span class="token punctuation">{</span>
  displayMode<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">,</span>
  macros<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    <span class="token string">"\\RR"</span><span class="token punctuation">:</span> <span class="token string">"\\mathbb{R}"</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="font-size-and-lengths">Font size and lengths</h4>
<p>By default, KaTeX math is rendered in a 1.21× larger font than the surrounding<br>
context, which makes super- and subscripts easier to read. You can control<br>
this using CSS, for example:</p>
<pre class=" language-css"><code class="prism  language-css"><span class="token selector"><span class="token class">.katex</span> </span><span class="token punctuation">{</span> <span class="token property">font-size</span><span class="token punctuation">:</span> <span class="token number">1.1</span>em<span class="token punctuation">;</span> <span class="token punctuation">}</span>
</code></pre>
<p>KaTeX supports all TeX units, including absolute units like <code>cm</code> and <code>in</code>.<br>
Absolute units are currently scaled relative to the default TeX font size of<br>
10pt, so that <code>\kern1cm</code> produces the same results as <code>\kern2.845275em</code>.<br>
As a result, relative and absolute units are both uniformly scaled relative<br>
to LaTeX with a 10pt font; for example, the rectangle <code>\rule{1cm}{1em}</code> has<br>
the same aspect ratio in KaTeX as in LaTeX.  However, because most browsers<br>
default to a larger font size, this typically means that a 1cm kern in KaTeX<br>
will appear larger than 1cm in browser units.</p>

