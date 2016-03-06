# Content Extract and Chrome Removal #

One of the most compelling features of Spinn3r is the ability to remove chrome and isolate only the specific content on a given HTML page. Many sources include only a summary, but not the full RSS content. For a full text search engine this might be fatal and you could end up missing content.

Most mainstream websites only include a summary in their RSS feed. For example, CNN has RSS feeds but they only have a one line description instead of the full content of the post.

What's the point of building a complicated search engine when you're missing 95% of the content on the web?

This has been a problem in the past with RSS search engines such as Feedster or Google Blog Search - why use a search engine that doesn't display all of the page content?

We're also seeing the same thing with a number of the A-list blogs. RSS feeds turn into a liability when bandwidth increases significantly every month with each new user. The more traffic a blog gets, the greater the probability that they'll enable partial RSS feeds to reduce their bandwidth costs and increase click through rates.

Spinn3r fetches the full HTML of this post, extracts the raw body of the post, and allows you to index the content without including any of the sidebar chrome which would just yield a false positive result in your algorithms.

It does this by using an internal content probability model and by scanning the HTML to determine what's potentially content and what's potentially a navigation item.

Indexing the sidebar content/chrome could seriously confuse your algorithms. For example, content clustering algorithms will cluster content from the same websites if they have similar and large amounts of sidebar content.

It goes without saying that this content should be used within fair use guidelines. Most of our customers ship search engines, memetrackers, and content analytics tools that index the full content but only include a snippet from the original in the actual result.

# In Action #

For a visual example, you can see the attached screenshot of a page with content highlighted in yellow. This screenshot was generated by passing our content extraction algorithm over this article on CNN.

This method isn't always 100% accurate. It has a small probability of false negatives for the first few words of a post. As such, it's meant for consumption by algorithms and not by humans.

# Standards Based #

To increase accuracy we also implement Google ad section targeting and hAtom entry-content which help us focus on the body of the post.

We also support Yahoo's robots-nocontent to help with HTML chrome/sidebar elimination.

About 15% of our content is indexed with these additional methods.

![http://spinn3r-client.googlecode.com/files/content-extract-example1-thumb.jpg](http://spinn3r-client.googlecode.com/files/content-extract-example1-thumb.jpg)