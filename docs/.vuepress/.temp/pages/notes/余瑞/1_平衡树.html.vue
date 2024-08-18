<template><div><h2 id="_1-选择一个数更改-查询" tabindex="-1"><a class="header-anchor" href="#_1-选择一个数更改-查询"><span>1.选择一个数更改，查询</span></a></h2>
<div class="language-c++ line-numbers-mode" data-highlighter="prismjs" data-ext="c++" data-title="c++"><pre v-pre><code><span class="line">#include&lt;bits/stdc++.h&gt;</span>
<span class="line">#define int long long</span>
<span class="line">void solve(){</span>
<span class="line">	int n;std::cin&gt;&gt;n;</span>
<span class="line">	std::vector&lt;int&gt;a(n);</span>
<span class="line">	std::multiset&lt;int&gt;s,v;</span>
<span class="line">	auto add = [&amp;](int x){</span>
<span class="line">            auto it = s.lower_bound(a[x]);</span>
<span class="line">            if (it != s.end())</span>
<span class="line">                v.insert(*it - a[x]);</span>
<span class="line">            if (it != s.begin()){</span>
<span class="line">                v.insert(a[x] - *prev(it));</span>
<span class="line">            }</span>
<span class="line">            if (it != s.begin() &amp;&amp; it != s.end()){</span>
<span class="line">                v.erase(v.lower_bound(*it - *prev(it)));</span>
<span class="line">            }</span>
<span class="line">            s.insert(a[x]);</span>
<span class="line">        };</span>
<span class="line"> </span>
<span class="line">        auto del = [&amp;](int x){</span>
<span class="line">            s.erase(s.lower_bound(a[x]));</span>
<span class="line">            auto it = s.lower_bound(a[x]);</span>
<span class="line">            if (it != s.end())</span>
<span class="line">                v.erase(v.lower_bound(*it - a[x]));</span>
<span class="line">            if (it != s.begin()){</span>
<span class="line">                v.erase(v.lower_bound(a[x] - *prev(it)));</span>
<span class="line">            }</span>
<span class="line">            if (it != s.begin() &amp;&amp; it != s.end()){</span>
<span class="line">                v.insert(*it - *prev(it));</span>
<span class="line">            }</span>
<span class="line">        };</span>
<span class="line">	for(int i=0;i&lt;n;i++){</span>
<span class="line">		std::cin&gt;&gt;a[i];</span>
<span class="line">		s.insert(a[i]);</span>
<span class="line">	}</span>
<span class="line">	auto b=a;</span>
<span class="line">	std::sort(b.begin(),b.end());</span>
<span class="line">	for(int i=1;i&lt;n;i++){</span>
<span class="line">		v.insert(b[i]-b[i-1]);</span>
<span class="line">	}</span>
<span class="line">	int m;std::cin&gt;&gt;m;</span>
<span class="line">	for(int i=0,x,y;i&lt;m;i++){</span>
<span class="line">		std::cin&gt;&gt;x&gt;&gt;y;</span>
<span class="line">		x--;</span>
<span class="line">		del(x);</span>
<span class="line">		a[x]=y;</span>
<span class="line">		add(x);</span>
<span class="line">		if(n==1){</span>
<span class="line">			std::cout&lt;&lt;a[0]&lt;&lt;&quot; &quot;;</span>
<span class="line">		}else{</span>
<span class="line">			std::cout&lt;&lt;*s.rbegin()+*v.rbegin()&lt;&lt;&quot; &quot;;</span>
<span class="line">		}</span>
<span class="line">	}</span>
<span class="line">	std::cout&lt;&lt;'\n';</span>
<span class="line">}</span>
<span class="line">signed main() {</span>
<span class="line">	std::ios::sync_with_stdio(false);std::cin.tie(nullptr);std::cout.tie(nullptr);</span>
<span class="line">	int t=1;</span>
<span class="line">	std::cin&gt;&gt;t;</span>
<span class="line">	while(t--){</span>
<span class="line">	   solve();</span>
<span class="line">	}</span>
<span class="line">}</span>
<span class="line"></span></code></pre>
<div class="line-numbers" aria-hidden="true" style="counter-reset:line-number 0"><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div></div></div></div></template>


