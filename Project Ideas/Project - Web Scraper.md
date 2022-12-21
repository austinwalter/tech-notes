# Web Scraper Outline

* Submit URL address
* Article.find_or_create_by_url()
* Parse URL, check if valid address
* Check if URL valid in Public Suffix Registry
* Standardize URL address (check if domain is blacklisted)
* Check if URL already exists in database
* If not, check for URL with case insensitive path, then alternate subdomains
* If an alternate URL is found
  * check if server responds on submitted & found URLs
  * if one redirects to the other submit main URL as canonical & other as alternate
  * if alternate doesn't respond, exit
  * if both respond but don't redirect, scrape content from both
  * check scraped content for canonical links and assign based on canonical links
  * if no canonical links or neither match correctly, retain submitted URL & content
* If no alternate URL is found
  * check if server responds
* Now URL should be valid, server responds, and no matches in database
* Create Domain (if doesn't already exist)
* Create URL
* If content wasn't already scraped, scrape content
* Create Article
  * Check if URL already assigned to other Article
  * Lock Articles when adding URLs? (possible race condition)


## Article Scraping System

* Scheduled Job Runner (Web Runner, RSS Runner)
* Article URL address parser & validator
* Blacklist System & Domain/URL standardizer
* RSS Reader/Runner
* Topic/Category Interpreter
* Article & HTML content scraper & canonical URL & RSS scraper
* RSS feed finder
  * example.com/feed
  * "rss" anchor link



Add `status` attribute to **Url** model
  * (inherit, allowed, blocked)
Update status Attribute for Domain model
  (allowed, blocked)
Create callback service/job to update all derived URLs
  * when a Domain status is canged
Add inherit_status to Url model
