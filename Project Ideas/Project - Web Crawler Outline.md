# Web Crawler Outline

Organization
	has many `Authors` through `Affiliations`
	has many `Articles`
	has one `CanonicalUrl`  as type `Url`

Author
	has many `Organizations` through `Affiliations`
	has many `Articles` through `Attributions`
	has many `WebPages`
	has many `Urls`  through `WebPages`
	has one `CanonicalUrl`  as type `Url`

WebPage
	has one `Organization`
	has many `Authors` 
	has one `Subject` as type `Article` or `PodcastEpisode`
	has one `CanonicalUrl`  as type `Url`
	has many `Urls` 

Article
	has one `Organization`
	has many `Authors` through `Attributions`
	has many `WebPages`
	has many `Urls`  through `WebPages`
	has one `CanonicalUrl`  as type `Url`

PodcastEpisode
	has one `Organization`
	has many `Authors` through `Attributions`
	has one `PodcastSeries`
	has many `WebPages`
	has many `Urls`  through `WebPages`
	has one `CanonicalUrl` as type `Url`

PodcastSeries
	has one `Organization`
	has many `Authors`
	has many `PodcastEpisodes`
	has many `WebPages`
	has many `Urls`  through `WebPages`
	has one `CanonicalUrl` as type `Url`


