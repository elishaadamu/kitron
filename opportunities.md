---
layout: default
header_image: "/assets/images/bg/blog-bg.jpg"
title: "Youth Opportunities"
description: ""
permalink: /youth-opportunities
---

{% include page_header.html %}

<section class="section">
	<div class="container">
		<div class="row justify-content-center">
			{% for post in site.opportunities %}
			<div class="col-lg-4 col-md-6">
				<div class="blog-item mb-5">
					{% if post.post_image %}
					<div class="blog-img position-relative">
						<a href="{{post.url | relative_url}}.html"><img src="{{post.post_image | relative_url}}" alt="{{post.title}}" class="img-fluid w-100" /></a>
					</div>
					{% endif %}
					<h4 class="mt-4 mb-2"><a href="{{post.url | relative_url}}.html">{{post.title}}</a></h4>
					<div class="post-meta text-uppercase mb-3">
						{% if post.author %}
						<a href="#" class="text-color">by {{post.author}} </a>
						{% endif %}
						<span class="text-color">{{post.date | date_to_long_string }}</span>
					</div>
					<p>{{post.excerpt | strip_html | truncatewords: "200"}}</p>
				</div>
			</div>
			{% endfor %}
		</div>
		{% include pagination.html %}
	</div>
</section>
