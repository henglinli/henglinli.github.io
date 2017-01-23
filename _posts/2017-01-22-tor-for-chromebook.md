---
layout: default
title: TOR for chromebook
comments: true
---
# [](#header-1) TOR for chromebook / chromebook可用的TOR分享
Dowload [this](/assets/binary/tor.tar.gz) tarball and extarct to /usr/local/ then run it, tested on HP chromebook 13 G1.

下载该tar包[tor.tar.gz](/assets/binary/tor.tar.gz) 解压执行即可, 于HP chromebook 13 G1上测试过。

`wget https://github.com/henglinli/henglinli.github.io/blob/master/assets/binary/tor.tar.gz`

`sudo tar -C /usr/local -xzf ~/Downloads/tor.tar.gz # where it is`

`cd /usr/local && ./tor -f torrc`

 version / 版本 ：
 
 `Tor 0.3.0.1-alpha @ Libevent 2.0.22-stable, OpenSSL 1.1.0c and Zlib 1.2.10`
 
 cation / 注意 ：
  
 In torrc meek-client is default at /usr/local/tor / torrc中meek-client默认配置到/usr/local/tor
 
 `UseBridges 1`
 
 `Bridge meek 0.0.2.0:2 url=https://d2zfqthxsdq309.cloudfront.net front=a0.awsstatic.com`
 
 `ClienttransportPlugin meek exec /usr/local/tor/meek-client`
  
{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a>
  {% else %}
    <span>&laquo; Prev</span>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <em>{{ page }}</em>
    {% elsif page == 1 %}
      <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a>
    {% else %}
      <a href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a>
  {% else %}
    <span>Next &raquo;</span>
  {% endif %}
</div>
{% endif %}
{% if page.comments %}
<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = "{{ page.url }}";
this.page.identifier = "{{ page.id }}";
};
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//EXAMPLE.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %} 
