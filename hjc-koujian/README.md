# Hjc Theme

This is a new theme for hjc

## Plugins

The theme support the following "plugins", with the variables used in the `pelicanconf.py` configuration file : 
	
- Disqus : `DISQUS_SITENAME` 
- Google Analytics : `GOOGLE_ANALYTICS`

## New Variables

We add some new functionalities, so we need to add some variables in the `pelicanconf.py` configuration file : 

- Twitter : To configure the publication of tweets, the `TWITTER_USERNAME` was added
- Avatar : The avatar on the sidebar is set with the `AVATAR` variable, set to the path to the image from the root of the website
- Digest : The digest displayed below the avatar is taken from the `SIDEBAR_DIGEST` variable
- The two Mozilla banners on the bottom of the website are set from the `FIREFOX_BANNERS` variable. There is a 'trick' with it. The variable is defined like that : 

	FIREFOX_BANNERS = (('banner_id', 'path_to_the_image', u'alt_text'),
					('banner_id', 'path_to_the_image', u'alt_text'))

From a "standard" firefox banner, the values are : 

	<a href="http://affiliates.mozilla.org/link/banner/{{ banner_id }}"><img src="{{ path_to_the_image }}" alt="{{ alt_text }}" /></a>

The `path_to_the_image` can be the remote file like given in the Affiliates Mozilla Website, but it won't work with my current Firefox Nightly version (Firefox 23). So I need to download the images and set the path to the local images.

## Twitter Card

I also add the support of Twitter Card.

On pages, the variables of the Twitter Card are set like that : 

	<meta name="twitter:card" content="summary">
	<meta name="twitter:site" content="{{ SITE_TITLE }}">
	<meta name="twitter:image" content="{{ AVATAR }}">

On the articles, we added these variables : 

	<meta name="twitter:creator" content="{{ article.author }}">
	<meta name="twitter:url" content="{{ SITEURL }}/{{ article.url }}">
	<meta name="twitter:title" content="{{ article.title }}">
	<meta name="twitter:description" content="{{ article.Summary }}">

The `article.summary` variable must be set on the header of the Rest/Markdown article source file (tag : `Summary:`). If not, the first `SUMMARY_MAX_LENGTH` words from the blog post will be used as a default summary.

## Icons

The social icons are from Font-Awesome, and colorized by myself.

Font Awesome by Dave Gandy - http://fortawesome.github.com/Font-Awesome
