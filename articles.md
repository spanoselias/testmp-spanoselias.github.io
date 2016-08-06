---
layout: default
title: Your New Jekyll Site
---

<div id="articles">
  <h1>Articles</h1>
  <ul class="posts noList">
    {% for post in site.posts %}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 120 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
</div>

{% if page.comments %}
	<!-- Java Script
   ================================================== -->
   <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
   <script>window.jQuery || document.write('<script src="js/jquery-1.10.2.min.js"><\/script>')</script>
   <script type="text/javascript" src="js/jquery-migrate-1.2.1.min.js"></script>  
   <script src="js/main.js"></script>
   <script type="text/javascript">
	   /* * * CONFIGURATION VARIABLES * * */
	   var disqus_shortname = 'Spanos';
	   /* * * DON'T EDIT BELOW THIS LINE * * */
	   (function() {
		   var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
		   dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
		   (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
	   })();
   </script>
   <noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{% endif %}
