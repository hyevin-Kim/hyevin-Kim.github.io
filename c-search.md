---
bg: './base/big-search.jpg'
layout: default
title: 'search'
crawlertitle: 'Search this site'
permalink: /c-search/
# summary:
active: search
---

<div class="nav-span nav-item">
	<form action="/search">
		<div class="tipue_search_left">
			<img
				src="/assets/images/base/search.png"
				class="tipue_search_icon"
			/>
		</div>
		<div class="tipue_search_right">
			<input type="text" id="search_input" required />
		</div>
		<div id="results-container" style="clear: both"></div>
	</form>
</div>

<!-- Script pointing to jekyll-search.js -->
<script
	src="/assets/js/simple-jekyll-search.js"
	type="text/javascript"
></script>

<script type="text/javascript">
	SimpleJekyllSearch({
		searchInput: document.getElementById('search_input'),
		resultsContainer: document.getElementById('results-container'),
		json: '/search.json',
		searchResultTemplate:
			'<article class="index-page"><a href="{url}" style="text-decoration:none" class="search-results">{title}</a></article>',
		noResultsText: 
			'<spen class="search-results">No results found</spen>',
		limit: 10000,
		fuzzy: false,
		exclude: ['Welcome'],
	})
</script>
