---
layout: default
title: emacs for chromebook
---
# [](#header-1) emacs for chromebook / chromebook可用的emacs

[emacs-25.1](https://github.com/henglinli/build-emacs/releases/download/25.1/emacs.tar.gz) travis build with --without-all --without-x --without-makeinfo, see also [.travis.yml](https://github.com/henglinli/build-emacs/blob/master/.travis.yml)

travis CI上采用参数--without-all --without-x --without-makeinfo构建的[emacs-25.1](https://github.com/henglinli/build-emacs/releases/download/25.1/emacs.tar.gz)，参见[.travis.yml](https://github.com/henglinli/build-emacs/blob/master/.travis.yml)

#### install location is /usr/local/emacs. libtinfo.so also packed.

#### 安装路径为/us/local/emacs。libtinfo.so 包含在压缩包中。

[1]: https://github.com/henglinli/build-emacs/releases/download/25.1/emacs.tar.gz "emacs-build release"
[2]: https://github.com/henglinli/build-emacs/blob/master/.travis.yml  "emacs-build .travis.yml"

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
