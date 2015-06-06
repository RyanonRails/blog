---
layout: page
title: About
sharing: false
---

Currently working as the Digital Experience Manager at [AMA - Alberta Motor Association](http://ama.ab.ca).


This weblog does not represent the thoughts, intentions, plans or strategies of my employer. It is solely my opinion.
All data and information provided on this site is for informational purposes only. ryanjones.io makes no representations
as to accuracy, completeness, currentness, suitability, or validity of any information on this site and will not be liable for any errors,
omissions, or delays in this information or any losses, injuries, or damages arising from its display or use. All information is provided on an as-is basis.

<br/>
<br/>
<div id="sub-nav">
	<div class="social">
		{% if site.facebook_user %}
		<a class="facebook" href="http://www.facebook.com/{{ site.facebook_user }}" title="Facebook">Facebook</a>
		{% endif %}
		{% if site.googleplus_user and site.googleplus_hidden == false %}
		<a class="google" href="https://plus.google.com/{{ site.googleplus_user }}" rel="author" title="Google+">Google+</a>
		{% endif %}
		{% if site.twitter_user %}
		<a class="twitter" href="http://twitter.com/{{ site.twitter_user }}" title="twitter">Twitter</a>
		{% endif %}
		{% if site.github_user %}
		<a class="github" href="https://github.com/{{ site.github_user }}" title="github">GitHub</a>
		{% endif %}
		{% if site.pinterest_user %}
		<a class="pinterest" href="https://pinterest.com/{{ site.pinterest_user }}" title="Pinterest">Pinterest</a>
		{% endif %}
		{% if site.delicious_user %}
		<a class="delicious" href="http://delicious.com/{{ site.delicious_user }}" title="Delicious">Delicious</a>
		{% endif %}
		{% if site.pinboard_user %}
		<a class="pinboard" href="https://pinboard.in/u:{{ site.pinboard_user }}" title="Pinboard">Pinboard</a>
		{% endif %}
		{% if site.subscribe_rss %}
		<a class="rss" href="{{ site.subscribe_rss }}" title="rss">RSS</a>
		{% endif %}
    {% if site.linkedin_user %}
    <a class="linkedin" href="http://www.linkedin.com/in/{{ site.linkedin_user }}" title="linkedin">LinkedIn</a>
    {% endif %}
    {% if site.stackoverflow_user %}
    <a class="stackoverflow" href="http://stackoverflow.com/{{ site.stackoverflow_user }}" title="stackoverflow">Stackoverflow</a>
    {% endif %}
	</div>
</div>