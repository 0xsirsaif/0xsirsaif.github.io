---
layout: dir
title: 0xsirsaif.github.io/bookmarks
cmd: ls -lat
pwd: bookmarks
---

<nav class="term">
    total {{ site.data.bookmarks.size | plus: 2 }}
</nav>
<table class="term">
    <nav class="term">
        <tr class = "mobile-hidden">
            <td class = "term ls-la">drwxr-xr-x</td>
            <td class = "term ls-la num">32</td>
            <td class = "term ls-la author">0xsaif</td>
            <td class = "term ls-la">users</td>
            <td class = "term ls-la size">64</td>
            <td class = "term ls-la date">{{ site.time | date: "%b" }}&nbsp;{{ site.time | date: "%_e%t%Y" }}</td>
            <td class = "term ls-la"><a class="term-nav file" href="">.</a></td>
        </tr>
    </nav>
    <nav class="term">
        <tr class = "mobile-hidden">
            <td class = "term ls-la">drwxr-xr-x</td>
            <td class = "term ls-la num">32</td>
            <td class = "term ls-la author">0xsaif</td>
            <td class = "term ls-la">users</td>
            <td class = "term ls-la size">64</td>
            <td class = "term ls-la date">{{ site.time | date: "%b" }}&nbsp;{{ site.time | date: "%_e%t%Y" }}</td>
            <td class = "term ls-la"><a class="term-nav file" href="/index.html">..</a></td>
        </tr>
    </nav>

    {% for item in site.data.bookmarks %}
        <nav class="term">
        <tr>
            <td class = "term ls-la mobile-hidden">lrwxrwxrwx</td>
            <td class = "term ls-la mobile-hidden num">1</td>
            <td class = "term ls-la mobile-hidden author">0xsaif</td>
            <td class = "term ls-la mobile-hidden">users</td>
            <td class = "term ls-la mobile-hidden size">{{ item.title.size | default: 32 }}</td>
            <td class = "term ls-la date">{{ item.date | date: "%b" }}&nbsp;{{ item.date | date: "%_e%t%Y" }}</td>
            <td><a class="term-nav symlink" href="{{ item.url }}">{{ item.title }}</a>{% if item.author %} <span class="term-comment">by {{ item.author }}</span>{% endif %}</td>
        </tr>
        </nav>
    {% endfor %}
</table>
