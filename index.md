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
	}
	
	.vidContainer > * {
		flex: 1 0 auto;
	}
	
	.vidContainer .vidName {
		padding: 15px;
	}
	
	.vidContainer video {
		/* max-width: 480px;
		max-height: 320px; */
	}
	
	.video-js {
		width: 480px;
		height: 360px;
	}
</style>

<link href="//vjs.zencdn.net/7.3.0/video-js.min.css" rel="stylesheet">
<script src="//vjs.zencdn.net/7.3.0/video.min.js"></script>

{% assign videosAvailable = "" | split: ',' %}{% for video in site.static_files %}{% if video.path contains 'videos' %}{% assign videosAvailable = videosAvailable | push: video %}{% endif %}{% endfor %}
{% for video in videosAvailable %}
## {{ video.basename }}
<div class="vidContainer">
<video id="my-player" class="video-js" controls preload="auto" data-setup='{}'>
<source src="{{ video.path }}" type="video/mp4">
</video>
</div>
---
{% endfor %}
