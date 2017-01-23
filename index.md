---
layout: default
comments: true
---

## [](#header-2)Index/索引
*  [hello new blog/新博客]({% post_url 2017-01-04-hello-new-blog %})
*  [TOR for chromebook / chromebook可用的TOR分]({% post_url 2017-01-22-tor-for-chromebook %})

{% if page.comments %}
<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
this.page.url = {{page.url}};
this.page.identifier = {{page.id}};
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//EXAMPLE.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %} 
