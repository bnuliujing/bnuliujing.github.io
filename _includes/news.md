<h2 id="news" style="margin: 2px 0px -15px;">News</h2>

<div class="publications">
<ul style="margin-top: 15px; margin-bottom: 10px; padding-left: 20px;">

{% for item in site.data.news.main %}

<li style="margin-bottom: 8px;">
  <strong>{{ item.date }}</strong> &nbsp;{{ item.en }}
</li>

{% endfor %}

</ul>
</div>
