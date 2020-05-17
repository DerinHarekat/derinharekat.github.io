---
title: nireD takeraH
---

<style>
	.vidContainer {
		max-width: 480px;
		display: flex;
		flex-direction: column;
		margin: 30px;
		padding: 30px;
		border: 1px solid black;
	}
	
	.vidContainer > * {
		flex: 1 0 auto;
	}
	
	.vidContainer .vidName {
		padding: 15px;
	}
	
	.vidContainer video {
		max-width: 480px;
		max-height: 320px;
	}
</style>

{% assign videosAvailable = "" | split: ',' %}{% for video in site.static_files %}{% if video.path contains 'videos' %}{% assign videosAvailable = videosAvailable | push: video %}{% endif %}{% endfor %}
{% for video in videosAvailable %}
<div class="vidContainer">
<span class="vidName">{{ video.name }}</span>
<video controls>
<source src="{{ video.path }}" type="video/mp4">
</video>
</div>
{% endfor %}
